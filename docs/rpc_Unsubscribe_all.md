# Tx APIs

<!---
//uatnet.usdp.io/unsubscribe_all?
-- [BINANCE No details]
-- [https://tendermint.com/rpc/#/Websocket/unsubscribe_all]
-->

### UnsubscribeAll
Unsubscribe from all events


#### Return Type
```
type ResultUnsubscribeAll struct {
    Results *state.Responses
}
```

#### Example
Run the command:
```
curl 'http://localhost:26657/unsubscribe_all'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {}
}
```


