# Blockchain-based-Voting-System
It is a decentralized voting system written in solidity implemented on Ethereum Blockchain on a Test RPC network.
## Dependencies

* ethereumjs-testrpc 
* web3@0.20.1
* solc

Install missing dependencies with [npm](https://www.npmjs.com/). 

```
> npm install ganache-cli web3@0.20.2
> node modules/.bin/ganache-cli
```

## Usage


Run the following commands to open the node console then deploy your contract to the test chain

```
Mukul:~/Election$ node
> Web3 = require('web3')
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)
> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)
> VotingContract = web3.eth.contract(abiDefinition)
> byteCode = compiledCode.contracts[':Voting'].bytecode
> deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
> deployedContract.address
> contractInstance = VotingContract.at(deployedContract.address)
