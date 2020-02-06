# Query APIs

### Query Tx
Get transactions by hash. Tx allows you to query the transaction results. nil could mean the transaction is in the mempool, invalidated, or was not sent in the first place.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| hash | []byte | nil | true    | transaction Hash to retrive |
| prove | bool | false | false     | Include proofs of the transactions inclusion in the block |



#### Return Type
Returns a transaction matching the given transaction hash.
```
type ResultTx struct {
    Hash     cmn.HexBytes          //hash of the transaction
    Height   int64                  //height of the block where this transaction was in
    Index    uint32                 //index of the transaction
    TxResult abci.ResponseDeliverTx //the `abci.Result` object
    Tx       types.Tx               //the transaction
    Proof    types.TxProof          //the `types.TxProof` object
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/tx?hash=0x79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
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
    "tx": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"
  }
}
```
