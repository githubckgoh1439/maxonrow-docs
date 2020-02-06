# Query APIs

### Query Block
Get block at a given height. If no height is provided, it will fetch the latest block.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| height | int64 | false | false    | height of blockchain |

#### Return Type
```
type ResultBlock struct {
    BlockMeta *types.BlockMeta
    Block     *types.Block
}
// BlockMeta contains meta information about a block - namely, it's ID and Header.
type BlockMeta struct {
    BlockID BlockID
    Header  Header
}
// Block defines the atomic unit of a Tendermint blockchain.
type Block struct {
    mtx        sync.Mutex
    Header     `json:"header"`
    Data       `json:"data"`
    Evidence   EvidenceData
    LastCommit *Commit
}
```

#### Example
Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "block",
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
    "block_meta": {
      "block_id": {
        "hash": "1C615DE531EF5A1942E4615F78D9F35DE84364BA4BBAE69CD6079B102D4DBDFD",
        "parts": {
          "total": "1",
          "hash": "D74ED6766BF8636CFC3254CFC24555F1110A2B83909FBD8E7D91E43464EFC51D"
        }
      },
      "header": {
        "version": {
          "block": "10",
          "app": "0"
        },
        "chain_id": "maxonrow-chain",
        "height": "250",
        "time": "2019-10-09T04:02:16.19724Z",
        "num_txs": "1",
        "total_txs": "1",
        "last_block_id": {
          "hash": "5729518E8822DBAC0EE8CFAB8611DA7B8AE869E07291ECCB0BED9708771E2975",
          "parts": {
            "total": "1",
            "hash": "2AD3BA4B2EFE7DA324DBF1C32FC9068C03991293C5E04D6188988532F94E683A"
          }
        },
        "last_commit_hash": "EACEB08EAC29641F6D1E1FC839266CEDE8FEBDF6A79377EA85C840660A4C8719",
        "data_hash": "C5FFE7245DDDB3B80637863EFD86AB1E35F790DA9A38C703F84FF6760F448860",
        "validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
        "next_validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
        "consensus_hash": "048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F",
        "app_hash": "83CE21DF09121CA295A0B82BFD391CAAB61BF692B0C728FFF7DAFF1906463436",
        "last_results_hash": "",
        "evidence_hash": "",
        "proposer_address": "CE9CA702BE3125D62B062BB925A552882CBC08CA"
      }
    },
    "block": {
      "header": {
        "version": {
          "block": "10",
          "app": "0"
        },
        "chain_id": "maxonrow-chain",
        "height": "250",
        "time": "2019-10-09T04:02:16.19724Z",
        "num_txs": "1",
        "total_txs": "1",
        "last_block_id": {
          "hash": "5729518E8822DBAC0EE8CFAB8611DA7B8AE869E07291ECCB0BED9708771E2975",
          "parts": {
            "total": "1",
            "hash": "2AD3BA4B2EFE7DA324DBF1C32FC9068C03991293C5E04D6188988532F94E683A"
          }
        },
        "last_commit_hash": "EACEB08EAC29641F6D1E1FC839266CEDE8FEBDF6A79377EA85C840660A4C8719",
        "data_hash": "C5FFE7245DDDB3B80637863EFD86AB1E35F790DA9A38C703F84FF6760F448860",
        "validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
        "next_validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
        "consensus_hash": "048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F",
        "app_hash": "83CE21DF09121CA295A0B82BFD391CAAB61BF692B0C728FFF7DAFF1906463436",
        "last_results_hash": "",
        "evidence_hash": "",
        "proposer_address": "CE9CA702BE3125D62B062BB925A552882CBC08CA"
      },
      "data": {
        "txs": [
          "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"
        ]
      },
      "evidence": {
        "evidence": null
      },
      "last_commit": {
        "block_id": {
          "hash": "5729518E8822DBAC0EE8CFAB8611DA7B8AE869E07291ECCB0BED9708771E2975",
          "parts": {
            "total": "1",
            "hash": "2AD3BA4B2EFE7DA324DBF1C32FC9068C03991293C5E04D6188988532F94E683A"
          }
        },
        "precommits": [
          {
            "type": 2,
            "height": "249",
            "round": "0",
            "block_id": {
              "hash": "5729518E8822DBAC0EE8CFAB8611DA7B8AE869E07291ECCB0BED9708771E2975",
              "parts": {
                "total": "1",
                "hash": "2AD3BA4B2EFE7DA324DBF1C32FC9068C03991293C5E04D6188988532F94E683A"
              }
            },
            "timestamp": "2019-10-09T04:02:16.19724Z",
            "validator_address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
            "validator_index": "0",
            "signature": "6Lc2zEJ5+mIesdr1LFCyV1lFtuePRUswSkxMzJCI57cku1iLqVKZo4SrKfqPiFUP3sI6EOD30nu0QfMXpZv8BA=="
          }
        ]
      }
    }
  }
}
```
