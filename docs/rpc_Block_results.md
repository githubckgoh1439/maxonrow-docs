# Query APIs

### Query BlockResults
BlockResults gets ABCIResults at a given height. If no height is provided, it will fetch results for the latest block. Results are for the height of the block containing the txs. Thus response.results[5] is the results of executing getBlock(h).Txs[5]

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| height | int64 | false | false   | height to return. If no height is provided, it will fetch informations regarding the latest block. 0 means latest |



#### Return Type
```
type ResultBlockResults struct {
    Height  int64
    Results *state.ABCIResponses
}
```

#### Example
Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "block_results",
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
    "height": "250",
    "results": {
      "deliver_tx": [
        {
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
        }
      ],
      "end_block": {
        "validator_updates": null
      },
      "begin_block": {
        "events": [
          {
            "type": "transfer",
            "attributes": [
              {
                "key": "cmVjaXBpZW50",
                "value": "bXh3MWp2NjVzM2dycWY2djZqbDNkcDR0NmM5dDlyazk5Y2Q4dXk5MjNu"
              },
              {
                "key": "YW1vdW50"
              }
            ]
          },
          {
            "type": "message",
            "attributes": [
              {
                "key": "c2VuZGVy",
                "value": "bXh3MTd4cGZ2YWttMmFtZzk2MnlsczZmODR6M2tlbGw4YzVsdHp6a24z"
              }
            ]
          },
          {
            "type": "commission",
            "attributes": [
              {
                "key": "YW1vdW50"
              },
              {
                "key": "dmFsaWRhdG9y",
                "value": "bXh3dmFsb3BlcjF1cmF6ejZ2dWxkanAwOWd0emZ0MG53Mmt1djI1bDA3OWZoOTlnNA=="
              }
            ]
          },
          {
            "type": "rewards",
            "attributes": [
              {
                "key": "YW1vdW50"
              },
              {
                "key": "dmFsaWRhdG9y",
                "value": "bXh3dmFsb3BlcjF1cmF6ejZ2dWxkanAwOWd0emZ0MG53Mmt1djI1bDA3OWZoOTlnNA=="
              }
            ]
          }
        ]
      }
    }
  }
}
```

