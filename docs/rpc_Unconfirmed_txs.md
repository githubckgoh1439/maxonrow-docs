# Query APIs

<!---
//uatnet.usdp.io/unconfirmed_txs?limit=_
-- [BINANCE No details]
-- [https://tendermint.com/rpc/#/Info/unconfirmed_txs]
-->

### Query UnconfirmedTxs
Get list of unconfirmed transactions

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| limit | int | 30 | false    | Maximum number of unconfirmed transactions to return |

#### Return Type
List of unconfirmed transactions
```
type ResultQueryUnconfirmedTxs struct {
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
    "method": "unconfirmed_txs",
    "params": ["1"],
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
    "n_txs": "0",
    "total": "0",
    "total_bytes": "0",
    "txs": []
  }
}
```

