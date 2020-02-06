# Query APIs

### Query Status
Get Tendermint status including node info, pubkey, latest block hash, app hash, block height and time.

#### Return Type
```
type ResultStatus struct {
    NodeInfo      p2p.DefaultNodeInfo
    SyncInfo      SyncInfo
    ValidatorInfo ValidatorInfo
}
```

#### Example
Run the command:
```
curl 'localhost:26657/status'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "node_info": {
      "protocol_version": {
        "p2p": "7",
        "block": "10",
        "app": "0"
      },
      "id": "13d45324d870a0bcb93affb09ea58a774338aafd",
      "listen_addr": "tcp://0.0.0.0:26656",
      "network": "maxonrow-chain",
      "version": "0.32.2",
      "channels": "4020212223303800",
      "moniker": "gohck.local",
      "other": {
        "tx_index": "on",
        "rpc_address": "tcp://127.0.0.1:26657"
      }
    },
    "sync_info": {
      "latest_block_hash": "9882052FF69F928B1697FCE6C8F0BAB9DABC374C93EF56820E864E4126AF1590",
      "latest_app_hash": "7F8A730CAB95686CD6935842089B1E2ED7AE13F3E20E13677120FE26A4E91B0E",
      "latest_block_height": "2290",
      "latest_block_time": "2019-10-09T10:32:17.999343Z",
      "catching_up": false
    },
    "validator_info": {
      "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
      "pub_key": {
        "type": "tendermint/PubKeyEd25519",
        "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
      },
      "voting_power": "100"
    }
  }
}
```
