# Tx APIs

<!---
//uatnet.usdp.io/unsubscribe?query=_
-- [BINANCE No details]
-- [https://tendermint.com/rpc/#/Websocket/unsubscribe]
-->

### Unsubscribe
Unsubscribe from event

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| query  | string | false | true    | query is a string, which has a form: "condition AND condition ..." (no OR at the moment).  |


#### Return Type
```
type ResultUnsubscribe struct {
    Results *state.Responses
}
```

#### Example
Run the command:
```
curl 'http://localhost:26657/unsubscribe'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {}
}
```

