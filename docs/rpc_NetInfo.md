# Query APIs

### Query NetInfo
Get network info.

#### Return Type
```
type ResultNetInfo struct {
    Listening bool     `json:"listening"`
    Listeners []string `json:"listeners"`
    NPeers    int      `json:"n_peers"`
    Peers     []Peer   `json:"peers"`
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/net_info'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "listening": true,
    "listeners": [
      "Listener(@)"
    ],
    "n_peers": "0",
    "peers": []
  }
}
```

