# ToDo List DApp
A todo list powered by Ethereum smart contracts. 


## Install
0. Install required packages.
```
npm install -g ganache-cli truffle
```
1. Run a `ganache-cli` service.
```
ganache-cli
## Or fill out .env file parameters for deploying contract on Rinkeby testnet
# cp sample.env .env
# nano .env
## Optionally you can run ganache localy with provided mnemonic phrase
# . .env
# ganache-cli --mnemonic "$MNEMONIC"
```
2. Navigate to `blockchain` directory and type below command and enter.
```
cd blockchain
npm install
truffle migrate --reset --compile-all --network development
## Deploy project on Rinkeby testnet
# truffle migrate --reset --compile-all --network rinkeby
```
3. Then navigate to `client` directory to enter below commands.
```
cd ../client
npm install
npm run serve
