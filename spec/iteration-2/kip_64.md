# [⏎](README.md#Roadmap) KIP_64
> Global Token Transfers Freeze

Crate a governance process allowing for freezing all token transfers based on whitelist and blacklist. If whitelist is active then all whitelisted assets can be transferred freely. If blacklist is active then tokens included in the blacklist will not be transferable. 

If tokens are frozen then user accounts should not be able to use them for any purpose with exception for KEX, which must be possible to be used as fee payments, so its still possible to vote and create governance proposals.

In this KIP an appropriate governance permissions should be created, allowing to create a "freeze assets proposal" and separate permission allowing for voting on the freeze proposal.
