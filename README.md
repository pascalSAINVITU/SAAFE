# SAAFE
## Safe Autonomous Agent Forwarding Estate

Inspired by the Bank with Secret of Obbie Barborico, this AA can completely safely store any assets with a very synthetic code. The assets can be as safely withdraw by anyone in possession of the private key associated to the public one used to stored the funds.

It can be use for cold storage of any assets (including BlackBytes).

## Example:
Send assets to SAAFE with :
* puk = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE90U9sMxra8wxIaIBy87p09aM8n4rKe1eZOtL0Im19ItIIzT3AiKE0dRsHemcn5bUcSqnC/jC+3H8vaCtjn9ylg==

Then from an other address, order the withdraw to the adress 'O7NYCFUL5XIJTYE3O4MKGMGMTN6ATQAJ' by sending to SAAFE the same puk, the withdrawing address as well as the signature of the message containing the withdrawing address:
* puk = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE90U9sMxra8wxIaIBy87p09aM8n4rKe1eZOtL0Im19ItIIzT3AiKE0dRsHemcn5bUcSqnC/jC+3H8vaCtjn9ylg==
* ad = O7NYCFUL5XIJTYE3O4MKGMGMTN6ATQAJ
* s = MEQCIA3df2YnWjDVlNoq+vQlSLRDhH+ESeaIWnMUHfoC/G6LAiAA+FUe6DaLG8h0ilGagyq2zb+z71ZWUx3fpikeq+DU2Q==
Optionnaly:
* as = <asset name >
if the asset used to trigger the AA is not the one stored.
