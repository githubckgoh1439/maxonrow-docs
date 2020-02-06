# Query APIs
<!---
//uatnet.usdp.io/consensus_params?height=_
-- [BINANCE No details]
-- [https://tendermint.com/rpc/#/Info/consensus_params]
-->

### Consensus Parameters
Get consensus parameters.


#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| height | int | 0 | false    | height to return. If no height is provided, it will fetch commit informations regarding the latest block. 0 means latest |


#### Return Type
Consensus parameters results.
```
type ResultConsensusParameters struct {
    Results *state.Responses
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/consensus_params?height=250'
```

The above command returns JSON structured like this: 
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "block_height": "250",
    "consensus_params": {
      "block": {
        "max_bytes": "22020096",
        "max_gas": "-1",
        "time_iota_ms": "1000"
      },
      "evidence": {
        "max_age": "100000"
      },
      "validator": {
        "pub_key_types": [
          "ed25519"
        ]
      }
    }
  }
}
```

