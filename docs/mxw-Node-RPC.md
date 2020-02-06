# Node RPC
* 1 Connecting use your own local node
* 2 Protocols
* 3 Configuration
* 4 Arguments
    * 4.1 URI/HTTP
    * 4.2 JSONRPC/HTTP
* 5 RPC Endpoint List
* 6 APIs


### 1. Connecting use your own local node
This page assumes that you have your own node running locally, so examples here use localhost:26657 to represent using RPC commands on a local node.

### 2. Protocols
The following RPC protocols are supported:

* URI over HTTP
* JSONRPC over HTTP

### 3. Configuration
RPC can be configured by tuning parameters under [rpc] table in the $HOME/config/config.toml file or by using the --rpc.X command-line flags.

Default rpc listen address is tcp://0.0.0.0:26657. To set another address, set the laddr config parameter to desired value. CORS (Cross-Origin Resource Sharing) can be enabled by setting cors_allowed_origins, cors_allowed_methods, cors_allowed_headers config parameters.

### 4. Arguments
Arguments which expect strings or byte arrays may be passed as quoted strings, like "abc" or as 0x-prefixed strings, like 0x616263.

#### 4.1 URI/HTTP
```
curl 'localhost:26657/broadcast_tx_sync?tx=0xdb01f0625dee0a63ce6dc0430a14813e4939f1567b219704ffc2ad4df58bde010879122b383133453439333946313536374232313937303446464332414434444635384244453031303837392d34331a0d5a454252412d3136445f424e422002280130c0843d38904e400112700a26eb5ae9872102139bdd95de72c22ac2a2b0f87853b1cca2e8adf9c58a4a689c75d3263013441a1240598c3a74dc08d82d97668ed3523a105a2afb752c5be34d09fb5f3158d55db2f545a2466263cf80f02d1184dd50efc4d8a636a262909a632ebeddeaa426c092b218d2e518202a'
```
Response:
```
{
    "jsonrpc": "2.0",
    "id": "",
    "result": {
        "code": 0,
        "data": "7B226F726465725F6964223A22383133453439333946313536374232313937303446464332414434444635384244453031303837392D3433227D",
        "log": "Msg 0: ",
        "hash": "AB1B84C7C0B0B195941DCE9CFE1A54214B72D5DB54AD388D8B146A6B62911E8E"
    }
}
```

#### 4.2 JSONRPC/HTTP
JSONRPC requests can be POST'd to the root RPC endpoint via HTTP (e.g. http://localhost:26657/).
```
{
  "method": "broadcast_tx_sync",
  "jsonrpc": "2.0",
  "params": [
    "abc"
  ],
  "id": "xyz"
}
```

### 5. RPC Endpoint List
An HTTP Get request to the root RPC endpoint shows a list of available endpoints.
```
curl 'localhost:26657'
```
Response:

#### Available endpoints that don't require arguments:
```
/abci_info
/broadcast_evidence
/consensus_state
/dump_consensus_state
/genesis
/health
/net_info
/num_unconfirmed_txs
/status
/version
/whitelisted
```

#### Endpoints that require arguments:
```
/abci_query?path=_&data=_&prove=_
/account?address=_
/block?height=_
/block_result?height=_
/blockchain?minHeight=_&maxHeight=_
/broadcast_tx_async?tx=_
/broadcast_tx_commit?tx=_
/broadcast_tx_sync?tx=_
/commit?height=_
/consensus_params?height=_
/decode_tx?tx=_
/encode_and_broadcast_tx_async?json=_
/encode_and_broadcast_tx_commit?json=_
/encode_and_broadcast_tx_sync?json=_
/encode_tx?json=_
/is_whitelisted?address=_
/query_fee?tx=_
/subscribe?query=_
/tx?hash=_&prove=_
/tx_search?query=_&prove=_&page=_&per_page=_
/unconfirmed_txs?limit=_
/unsubscribe?query=_
/unsubscribe_all?
/validator?address=_
/validators?height=_
```
### 6. APIs