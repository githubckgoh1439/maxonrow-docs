# Query APIs

<!---
//uatnet.usdp.io/whitelisted?
----[goh sendiri] 
-->


### Query Whitelisted
Returns address of whitelisted.


#### Return Type
```
type ResultWhitelisted struct {
    Results [] string
}
```


#### Example
Run the command:
```
curl 'http://localhost:26657/whitelisted'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": [
    "mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e",
    "mxw1vulu4lra8nd2aswz60xkj5uxnp9kw0fuq3e65g",
    "mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
    "mxw1qqfh7ea0kv0dp7dng5ypg3tw9r03hqsa0m5saw",
    "mxw1qqd9z2dsdl09a5tehhwm4ettet4ra2f34axw5d",
    "mxw1qqsfkf92c097dr6va58c6fttvmx4lx8k8xalka"
  ]
} 
```

