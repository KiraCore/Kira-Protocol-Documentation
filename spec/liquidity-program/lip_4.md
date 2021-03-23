# [⏎](README.md#Roadmap) LIP_4
>  Interchain Registrar

Goal of this proposal is to implement a multi-directional peg-contract enabling token transfers and communication between uncapped number of decentralized networks.

Pegging is a mechanism of locking assets assets on chain `A` in order to issue them on chain the `B` and vice versa. Validators of both chains observe state of each other chains (e.g. account balance of peg-contract/module). If chain `A` validators notice asset `X` locked in the peg-contract on the chain `B` they can issue a 1:1 `aX` asset on their chain `A` representing that locked token. When asset is deposited to the peg-contract by the user, the transaction must include information such as destination chain and to which account pegged token should be deposited. 

## Implementation

#### Main Objectives
* `chain-id` and `controller` Accounts Registrar
* Bidirectional Value Transfers
  * ERC20