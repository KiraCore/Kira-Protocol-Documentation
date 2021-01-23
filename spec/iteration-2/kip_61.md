# [⏎](README.md#Roadmap) KIP_61
> Query Transactions

Crate a new tab or view similar to validator node explorer where it is possible to query transactions by their hash (single tx) as well as query all transactions within given block (list of many tx'es).

By default the view should display current block and all transactions accepted or rejected within that block.

It must be possible to easily distinguish between transactions which failed and those that succeeded (it might be required to generate failed tx'es to test that behavior). It would be ideal if different transaction types were visually distinguishable (interx should contain endpoint returning all tx types available)
