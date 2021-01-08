# [⏎](README.md#Roadmap) KIP_60
> Query Validators

Create `/valopers` endpoint incorporating detailed information in regards to all network actors recorded in the validators registry as per KIP_26.

## Example 
```
[ {
     "address": "kiraXXXXXXXXXXXXXXXX",
      "valkey": "kiravaloperXXXXXXXXXXXXXXXX"
      "pubkey": "kiravalconspubXXXXXXXXXXXXXXXXXXXXX",
     "moniker": <string>,
     "website": <string>,
      "social": <string>,
    "identity": <string>,
  "commission": <decimal>,
      "status": <string>,
        "rank": <Int64>,
      "streak": <Int64>,
   "mischance": <Int64>
  }, { ... }, ...
]
```
