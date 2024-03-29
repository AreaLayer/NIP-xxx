# NIP-xxx: Event Data

 `optional` `draft`

The NIP follows special events and respecting limits of Nostr protocol and Lightning Network

Based on NIP-01, NIP-02, NIP-04, NIP-09, NIP-28, NIP-46 and NIP-47

- Event A: Alice commbines with Bob open channel with him (E.g. DMs, Chat channel, etc)
- Event B: Bob accepts Alice and get together open a channel
- Event C: DLC verify both parties, multisigs, musig

## Definition

- `pp`: Tag must be present that indicate peer
- `p`: PubKey
- `event`: Tag indicates event inside chat on client
- `c`: Tag indicates open or close channel 
- `locktime`: Tag indicates when close channel with Locktime form
- `dlc`: Tag indicates DLCs and event
- `Kind:30090`: Event type

## PoC

We created a proof of conecpt around this idea 

[More details](https://github.com/AreaLayer/Lightning-lending-PoC/blob/main/poc.rs)


## Specs

- `Event A`: Two `pp` into `event`

- `Event B`: The two `pp` accepts open `c` or closec channel

- `Event C`: With `dlc`tag the DLCs verify both parties be multisig and musig

##  Implemenatation

Follow below the example of the NIP

```json
{
"id":"xxx"
"pubkey":"xxx"
"created_at":"xxx"
"kind":"xxx"
"input":"np12"
"output":"np13"
"pp":"np13"
"c":"np12"
"locktime":"block 78888"
"content":"xxx"
"sign":"xxx"
"dlc":"open block 6777 and close 78888"
"hex":"1282893"
"event":"event124"
},
```
## Signature

The signatures can happen with [NIP-46](https://github.com/nostr-protocol/nips/blob/master/46.md) using Nostr Connect allowign signatures safe between peers

## Compatibility

This NIP is compatible with NIP-01, NIP-02, NIP-04, NIP-09, NIP-28, NIP-46 and NIP-47 and relays/clients will need add only the `tag`:


- `pp`: Tag must be present that indicate peer
- `event`: Tag indicates event inside chat on client
- `c`: Tag indicates open or close channel 
- `locktime`: Tag indicates when close channel with Locktime form
- `dlc`: Tag indicates DLCs and event


