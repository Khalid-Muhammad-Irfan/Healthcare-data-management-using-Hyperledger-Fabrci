# Project

## Setup

Clone `fabric-samples` repository:
`git clone https://github.com/hyperledger/fabric-samples`

Install the binaries for Fabric v2.4.7:
`curl -sSL https://bit.ly/2ysbOFE | bash -s -- 2.4.7 1.5.5`

## Deployment

Bring up the network:

``` shell
cd fabric-samples/test-network && ./network.sh down
./network.sh up createChannel -ca -s couchdb
```

Deploy the smart contract:

``` shell
./network.sh deployCC -ccn private -ccp ../asset-transfer-private-data/chaincode-javascript/ -ccl javascript -ccep "OR('Org1MSP.peer','Org2MSP.peer')" -cccg ../asset-transfer-private-data/chaincode-javascript/collections_config.json
```

Run the app:

``` sh
cd fabric-samples/asset-transfer-private-data/application-javascript
npm i
node app.js
```

