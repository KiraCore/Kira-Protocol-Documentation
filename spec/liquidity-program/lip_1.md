# [⏎](README.md#Roadmap) SIP_1
>  ERC20 KEX

KEX is a native asset of the Kira Network, however before the Kira Network goes live we have to provide community with the early access to the market on the Ethereum blockchain. For that purpose we will deploy [ERC20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) placeholder token that will be in the future swapped in the manual way for the native Kira token. 

We must provide ability to mint additional tokens in case where we might want to provide 2 way centralized peg and long term preserve the Ethereum market.

We must have ability to freeze the token transfers if necessary (eg. to enforce token swap in the future or simultaneous market access). In such case only token transfers to and from a configurable list of addresses should be possible.

## Requirements

Token Name: `KIRA Network`
Initial Supply: `300'000'000`
Symbol: `KEX`
Decimals: `6`
Mintable: `Yes`
Freezing: `Yes with exception for curated list of addresses`

_NOTE: Token must have implementation fully compatible with the ERC20 standard as it is essential to be compatible with the uniswap v2._

## Upgrades

Token contract should be [upgradable](https://ethereum.stackexchange.com/questions/2404/upgradeable-smart-contracts) through proxy contract or other viable method, so that we can preserve ability to maintain the address in case changes would be required in the future. We must ensure that token contract remains compatible with uniswap v2.

_NOTE: If its not possible to create upgradable ERC20 that is compatible with uniswap we should skip the upgradeability feature and deploy a standard ERC20 contract as per provided spec_

## Testing

Code must be commented and full detailed documentation must pe provided regarding deployment and use of every function in form of the README.

Contract compatibility with uniswap v2 must be tested on the kovan testnet along all other features such as asset freeze, whitelist and additional tokens issuance.


