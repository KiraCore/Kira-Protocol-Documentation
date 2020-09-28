# [⏎](README.md#Roadmap) SIP_1
>  ERC20 KEX

KEX is a native asset of the Kira Network, however before the Kira Network goes live we have to provide community with the early access to the market on the Ethereum blockchain. For that purpose we will deploy [ERC20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) placeholder token that will be in the future swapped in the manual or half-automated way for the native Kira token. 

We must have ability to freeze the token transfers if necessary (eg. to enforce token swap in the future or simultaneous market access). In such case only token transfers to and from a configurable list of addresses should be possible.

## Requirements

Token Name: `KIRA Network`
Initial Supply: `300'000'000`
Symbol: `KEX`
Decimals: `6`
Freezing: `Yes with exception for curated list of addresses`
Whitelist: `Exception from the account freeze, should have 3 options: allow_deposit, allow_transfer, allow_all`
Transactions: `Must have multi-send capability for whitelist and token transfers`

_NOTE: Token must have implementation fully compatible with the ERC20 standard as it is essential to be compatible with the uniswap v2._

## Testing

Code must be commented and full detailed documentation must pe provided regarding deployment and use of every function in form of the README.

Contract compatibility with uniswap v2 must be tested on the kovan testnet along all other features such as asset freeze, whitelist and additional tokens issuance.


