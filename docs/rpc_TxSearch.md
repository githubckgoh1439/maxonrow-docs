# Query APIs

### Query TxSearch
TxSearch allows you to query for multiple transactions results.You could search transaction by its index. It returns a list of transactions (maximum ?per_page entries) and the total count.

#### Enable Indexer

You need to enable indexer in config.tml. You can modify the index_tags to tx.height, which is the only tag we support now. In this way, you can index transactions by height by adding "tx.height" tag here.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| query | string | " " | true   | Query |
| prove | bool | false | false   | Include proofs of the transactions inclusion in the block |
| page | int | 1 | false   | Page number (1-based) |
| per_page | int | 30 | false   | Number of entries per page (max: 100) |

#### Return Type
- proof: the types.TxProof object
- tx: []byte - the transaction
- tx_result: the abci.Result object
- index: int - index of the transaction
- height: int - height of the block where this transaction was in
- hash: []byte - hash of the transaction

#### Example
For example, if you want to search all the transations happened on height 250.

Run the command:
```
curl 'localhost:26657/tx_search?query="tx.height=250"&prove=true'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "txs": [
      {
        "hash": "79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9",
        "height": "250",
        "index": 0,
        "tx_result": {
          "log": "[{\"msg_index\":0,\"success\":true,\"log\":\"{\\\"hash\\\":\\\"79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9\\\",\\\"nonce\\\":0}\"}]",
          "gasUsed": "78131",
          "events": [
            {
              "type": "message",
              "attributes": [
                {
                  "key": "YWN0aW9u",
                  "value": "c2VuZA=="
                }
              ]
            },
            {
              "type": "message",
              "attributes": [
                {
                  "key": "RnJvbQ==",
                  "value": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw"
                },
                {
                  "key": "VG8=",
                  "value": "bXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRl"
                },
                {
                  "key": "QW1vdW50",
                  "value": "MTE="
                }
              ]
            },
            {
              "type": "system",
              "attributes": [
                {
                  "key": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw",
                  "value": "eyJoYXNoIjoiMmNhZGNmYjBjMzM2NzY5ZDUwM2Q1NTdiMjZmY2YxZTkxODE5ZTdlNSIsInBhcmFtcyI6WyJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJteHcxYWdsd2RlaGtyZ2FuOXA4NmVhOGtsNzVsa2FnMmgweHR3ajJkNGUiLCIxMSJdfQ=="
                }
              ]
            }
          ]
        },
        "tx": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04",
        "proof": {
          "RootHash": "C5FFE7245DDDB3B80637863EFD86AB1E35F790DA9A38C703F84FF6760F448860",
          "Data": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04",
          "Proof": {
            "total": "1",
            "index": "0",
            "leaf_hash": "xf/nJF3ds7gGN4Y+/YarHjX3kNqaOMcD+E/2dg9EiGA=",
            "aunts": []
          }
        }
      }
    ],
    "total_count": "1"
  }
}
```

