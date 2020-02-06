# Query APIs

<!---
//uatnet.usdp.io/validators?height=_
-- [BINANCE No details]
-- [https://cosmos.network/rpc/#/ICS0/get_validatorsets__height_]
-->


#### Query ValidatorsSetHeight 
Get validators set a certain height

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| height  | int | false | true    | Block height |


#### Return Type
```
type ResultValidatorsetHeight struct {
    Results *state.Responses
}
```

#### Example

Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "validators",
    "params": ["250"],
    "id": 0,
    "jsonrpc": "2.0"
}
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": {
    "block_height": "250",
    "validators": [
      {
        "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
        "pub_key": {
          "type": "tendermint/PubKeyEd25519",
          "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
        },
        "voting_power": "100",
        "proposer_priority": "0"
      }
    ]
  }
}
```

