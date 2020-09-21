# [⏎](README.md#Roadmap) KIP_47
> INTERX Response Caching

It is expected that responses such as tx hash, validator set queries, orderbook state and others are going to repeat often, we have to enable INTERX service to cache all queries on the disk or RAM memory to ensure minimal possible impact on the full node operations. 

Each individual endpoint should have a configurable time (`CACHING_DURATION` in seconds) during which query responses are persisted in the memory. Every time a request is made, the INTERX service should check if a record in memory does not contain the response.


## Implementation

1. Users sends request to the INTERX endpoint `E` with query parameters `P`
2. If endpoint `E` does not have caching enabled then full node is queried and response `R` with status code `C` is returned
3. If `E` has caching enabled, then INTERX calculates a hash `H = Blake2(E + P)`
4. We lookup `H` in the KV store of objects stored in memory or disk
    * Values within KV store are JSON objects containing expiration time `T`, block number `B`, `C` and `R`
5. If `H` is found the `R` is returned if `T` is greater than `TIME_NOW` or if block number `B` did not changed
    * Appropriate status code must be returned
    * If `H` is expired then object must be disposed from memory
6. If `H` is NOT found the full node is queried and response `R` cashed and returned
    * `R` is cached along `C`, `B` and `T = TIME_NOW + CACHING_DURATION`

## Further Considerations

* The `rpc_methods` endpoint must be modified to contain information regarding caching time duration as optional parameter.
* Every endpoint request (with exception for POST) must be cached, if `CACHING_DURATION` is set to `0` then minimum duration of caching is 1 block 
* We must be able to define maximum size (in MB) of the in-memory cache, if the limitation is reached then `10%` of objects stored should be deleted at random until sufficient memory is available.
