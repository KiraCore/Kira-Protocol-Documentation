# [⏎](README.md#Roadmap) LIP_3.1
>  Liquidity Auction Frontend

The crowdfunding auction frontend must enable participants realtime tracking of the auction progress and be accessible publicly a web application (ideally as static page or dynamic if that is not possible).

Page should consist of 2 sections
1. Realtime Stats & References
2. Realtime Chart


## Stats & References

We have to present following dynamic properties:
* Auction start - `DD:HH:MM:SS` countdown until auction starts
* Auction end - `DD:HH:MM:SS` countdown until auction ends
* Current KEX price in ETH and USD
* Current amount of ETH deposited
* Amount of KEX tokens to be distributed
* Deposit address with signature + reference how to verify deposit address

_NOTE: Auction End is based on the amount of assets contributed at any given point of time as per `KIP_3`_

## Chart

Chart has to demonstrate live price action / amount being raised until finalization of the auction.

![picture 1](https://i.imgur.com/z53UEmi.png)  

## Optional Features (if enough time to complete)

Would be ideal if user could validate if their address is whitelisted (can be done using a statically hosted file but some active query would be ideal if possible)

