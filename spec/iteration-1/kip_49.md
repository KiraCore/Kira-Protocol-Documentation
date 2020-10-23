# [⏎](README.md#Roadmap) KIP_49
> Transactions Challenge

One of the common pitfalls when sending transactions is mistyping addresses and sending money to accounts where user was coerced by the malicious application to input fictitious address (clipboard address swap, dependency injection, etc). We have to enable protection from such exploits if from of the challenge that can only be known by a second party communicating with user though separate communication channels.

## Execution

We have to enable creation of transactions with predefined `expiration` timestamp before which the transaction can be accepted by the receiving account. This mechanism can be conditional or unconditional. Meaning that additional `challenge` field can be present. If the `challenge` is not present then receiving account can send empty `challenge_response` transaction to claim the assets. If the `challenge_response` is not submitted then money will not be sent (effectively preventing user from sending money to non existing accounts by mistake). In the case where `challenge` is present then receiving account must send the `challenge_response` message containing solution to the `Blake2` hash riddle. Money will be send to the receiving account if correct solution is sent before `expiration` time.

## Security

We have to ensure that when `challenge` transaction is sent the assets in question become locked and unaccessible to any of the two parties. 