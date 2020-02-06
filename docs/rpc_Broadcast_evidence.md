# Query APIs
<!---
//uatnet.usdp.io/broadcast_evidence?evidence=_
----[https://tendermint.com/rpc/#/Info/broadcast_evidence]
-->

### Query BroadcastEvidence
Broadcast evidence of the misbehavior.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| evidence | string | false | true    | Amino-encoded JSON evidence |

#### Return Type
```
type ResultBroadcastEvidence struct {
    Results *state.Responses
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/broadcast_evidence'
```

The above command returns JSON structured like this:
```
{
  "error": "",
  "result": "",
  "id": "",
  "jsonrpc": "2.0"
}
```

