# [⏎](README.md#Roadmap) KIP_33
> Preview Validator Set

Frontend application must have a dedicated "Network" tab where users can preview validator set. We must be able to display detailed information in regards to all network operators.

As per KIP_26 validator set explorer tab should incorporate information from validator identity registry such as moniker, website, social media link but most importantly current validator rank as defined by the KIP_54. All validators in the tab should be sorted by their rank and each entry incorporate color-coded status indicator so that is easy to identify active and inactive validator nodes. 

Users should have ability to preview detailed information when expanding each entry as well as easily search validators by their address & moniker.

Users should have further ability to "star/unstar" or otherwise mark selected validator nodes they trust. If the node is marked as trusted then frontend application should query signer key registry as per KIP_4 to discover all enabled (active) entries which contain INTERX IP address'es and corresponding public keys. 

Frontend should monitor active INTERX nodes and loadbalance the requests, so that a single node is never spammed. 