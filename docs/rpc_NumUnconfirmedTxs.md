# Query APIs

### Query NumUnconfirmedTxs
Get number of unconfirmed transactions.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| limit | int | 30 | false    | Maximum number of entries (max: 100) |

#### Return Type
```
// List of mempool txs
type ResultUnconfirmedTxs struct {
    N   int
    Txs []types.Tx
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/num_unconfirmed_txs'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "n_txs": "0",
    "total": "0",
    "total_bytes": "0",
    "txs": null
  }
}
```

