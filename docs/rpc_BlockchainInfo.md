# Query APIs

### Query BlockchainInfo
Get block headers for minHeight <= height <= maxHeight. Block headers are returned in descending order (highest first).

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| minHeight | int64 | false | true   | Minimum block height of blockchain |
| maxHeight | int64 | false | true   | Maximum block height of blockchain |

#### Return Type
List of blocks
```
type ResultBlockchainInfo struct {
    LastHeight int64
    BlockMetas []*types.BlockMeta
}
```

#### Example
Run the command:
```
curl 'http://localhost:26657/blockchain?minHeight=250&maxHeight=252'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "last_height": "3027",
    "block_metas": [
      {
        "block_id": {
          "hash": "4E6A262CE71B6104FE6B2033672617DB824C6F9CB0F3758B629B8D2D1FED5105",
          "parts": {
            "total": "1",
            "hash": "C1B7A9105EEE1E6120021DBAF1EE25EF4EA05235EC7758DEDEA9E8390A41FF1A"
          }
        },
        "header": {
          "version": {
            "block": "10",
            "app": "0"
          },
          "chain_id": "maxonrow-chain",
          "height": "252",
          "time": "2019-10-09T04:02:26.360922Z",
          "num_txs": "0",
          "total_txs": "1",
          "last_block_id": {
            "hash": "275734B220949E522948D2D9D6E6A39899044CA141BFE03B993F643227EE7FF8",
            "parts": {
              "total": "1",
              "hash": "495A182D6B984EE937C02DDBD0A0A07C197022670B37CBADDA266C1BD10E3DED"
            }
          },
          "last_commit_hash": "AD8DAAEC538BEE9A5F1488AE415B333A9A2607643081974BE8CBEE7A442BBF5B",
          "data_hash": "",
          "validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
          "next_validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
          "consensus_hash": "048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F",
          "app_hash": "980D7CF4FF5920212329B4D0AE319565F70840AB225B65502790F04660F23CA9",
          "last_results_hash": "",
          "evidence_hash": "",
          "proposer_address": "CE9CA702BE3125D62B062BB925A552882CBC08CA"
        }
      },
      {
        "block_id": {
          "hash": "275734B220949E522948D2D9D6E6A39899044CA141BFE03B993F643227EE7FF8",
          "parts": {
            "total": "1",
            "hash": "495A182D6B984EE937C02DDBD0A0A07C197022670B37CBADDA266C1BD10E3DED"
          }
        },
        "header": {
          "version": {
            "block": "10",
            "app": "0"
          },
          "chain_id": "maxonrow-chain",
          "height": "251",
          "time": "2019-10-09T04:02:21.276513Z",
          "num_txs": "0",
          "total_txs": "1",
          "last_block_id": {
            "hash": "1C615DE531EF5A1942E4615F78D9F35DE84364BA4BBAE69CD6079B102D4DBDFD",
            "parts": {
              "total": "1",
              "hash": "D74ED6766BF8636CFC3254CFC24555F1110A2B83909FBD8E7D91E43464EFC51D"
            }
          },
          "last_commit_hash": "AC9ABF612D35EE807BF1FA0A950883B7830456138D045420FDACC20AD8C701CD",
          "data_hash": "",
          "validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
          "next_validators_hash": "8FA5DDBB4588748676C7D0F4D61EDD06424CE9C6E16BFD6604E6B25807501EC7",
          "consensus_hash": "048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F",
          "app_hash": "D1D69AE358EEFC277B99C504E92FB7D777C49AFF45A7283CB88D34089CA07CB6",
          "last_results_hash": "6E340B9CFFB37A989CA544E6BB780A2C78901D3FB33738768511A30617AFA01D",
          "evidence_hash": "",
          "proposer_address": "CE9CA702BE3125D62B062BB925A552882CBC08CA"
        }
      },
      {
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
      }
    ]
  }
}
```
