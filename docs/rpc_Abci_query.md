# Query APIs

### ABCIQuery
Query the application for some information.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| path | string | false | false    | Path to the data ("/a/b/c") |
| data | []byte | false | true     | Data |
| height | int64 | 0 | false    | Height (0 means latest) |
| prove | bool | false | false    | Include proofs of the transactions inclusion in the block, if true |


#### Available Query Path
- /store/acc/key
- /tokens/info
- /tokens/list
- /param/fees


#### Return Type
```
type ResponseQuery struct {
    Code                 uint32
    Log                  string
    Info                 string
    Index                int64
    Key                  []byte
    Value                []byte
    Proof                *merkle.Proof
    Height               int64
    Codespace            string
}
```

#### Example
In this example, we will explain how to query account info with abci_query. 1. Generate query key To get the correct key you need to ： The query key is : "account:" || address in hex. The first part is in ASCII.

Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

The above command returns JSON structured like this: 
```
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": {
    "response": {
      "value": "eyJuYW1lIjoiZGVmYXVsdCIsIm1pbiI6W3siZGVub20iOiJjaW4iLCJhbW91bnQiOiIxMDAwMDAwMDAwMDAwMDAwMCJ9XSwibWF4IjpbeyJkZW5vbSI6ImNpbiIsImFtb3VudCI6IjEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAifV0sInBlcmNlbnRhZ2UiOiIwLjA1IiwiaXNzdWVyIjoibXh3MXVyYXp6NnZ1bGRqcDA5Z3R6ZnQwbncya3V2MjVsMDc5M2M2bTl3In0=",
      "height": "2834"
    }
  }
}
```

