# Tx APIs

<!---
//uatnet.usdp.io/subscribe?query=_
-- [BINANCE No details]
-- [https://tendermint.com/rpc/#/Websocket/subscribe]
-->

### Subscribe
Subscribe for events

To tell which events you want, you need to provide a query. query is a
string, which has a form: "condition AND condition ..." (no OR at the
moment). 

Examples:

- tm.event = 'NewBlock' # new blocks
- tm.event = 'CompleteProposal' # node got a complete proposal
- tm.event = 'Tx' AND tx.hash = 'XYZ' # single transaction
- tm.event = 'Tx' AND tx.height = 5 # all txs of the fifth block
- tx.height = 5 # all txs of the fifth block


#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| query  | string | false | true    | query is a string, which has a form: "condition AND condition ..." (no OR at the moment).   |


#### Return Type
```
type ResultSubscribe struct {
    Results *state.Responses
}
```

#### Example
Run the command:
```
curl 'http://localhost:26657/subscribe'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {}
}
```
