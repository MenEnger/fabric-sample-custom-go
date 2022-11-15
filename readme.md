
# HyperLedger Fabricのチェーンコードのサンプル

公式のGoのサンプルにBrand属性を追加したものです。

前提：チュートリアル環境にてネットワーク起動、mychannel作成

```sh
export PATH=${PWD}/../bin:$PATH
export FABRIC_CFG_PATH=$PWD/../config/
# Environment variables for Org1

export CORE_PEER_TLS_ENABLED=true
export CORE_PEER_LOCALMSPID="Org1MSP"
export CORE_PEER_TLS_ROOTCERT_FILE=${PWD}/organizations/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt
export CORE_PEER_MSPCONFIGPATH=${PWD}/organizations/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp
export CORE_PEER_ADDRESS=localhost:7051

peer chaincode query -C mychannel -n basic -c '{"Args":["GetAllAssets"]}'
[{"ID":"asset1","color":"blue","size":5,"brand":"Nike","owner":"Tomoko","appraisedValue":300},{"ID":"asset2","color":"red","size":5,"brand":"Puma","owner":"Brad","appraisedValue":400},{"ID":"asset3","color":"green","size":10,"brand":"Adidas","owner":"Jin Soo","appraisedValue":500},{"ID":"asset4","color":"yellow","size":10,"brand":"Nike","owner":"Max","appraisedValue":600},{"ID":"asset5","color":"black","size":15,"brand":"Asics","owner":"Adriana","appraisedValue":700},{"ID":"asset6","color":"white","size":15,"brand":"Mizuno","owner":"Michel","appraisedValue":800}]

```
