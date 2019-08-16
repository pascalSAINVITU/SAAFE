# SAAFE
## Safe Autonomous Agent Forwarding Estate

Inspired by the Bank with Secret of Obbie Barborico, this AA can completely safely store any assets with a very synthetic code. The assets can be as safely withdraw by anyone in possession of the private key associated to the public one used to stored the funds.

It can be use for cold storage of any assets (including BlackBytes).

Unfortunately, public keys and signature are too long for a single field, so they have to be introduce in 2 parts, puk1, puk2, s1 and s2.

For example, send assets to SAAFE with puk = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE90U9sMxra8wxIaIBy87p09aM8n4rKe1eZOtL0Im19ItIIzT3AiKE0dRsHemcn5bUcSqnC/jC+3H8vaCtjn9ylg==
Then from an other address, order the withdraw to the adress 'O7NYCFUL5XIJTYE3O4MKGMGMTN6ATQAJ' by sending to SAAFE the same puk, the withdrawing address as well as the signature of the message containing the withdrawing address:


## Example:
Send assets to SAAFE with :
* puk1 = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE90U9sMxra8wxIaIBy87p09aM8n4r
* puk2 = Ke1eZOtL0Im19ItIIzT3AiKE0dRsHemcn5bUcSqnC/jC+3H8vaCtjn9ylg==

Then from an other address, order the withdraw to the adress 'O7NYCFUL5XIJTYE3O4MKGMGMTN6ATQAJ' by sending to SAAFE the same puk, the withdrawing address as well as the signature of the message containing the withdrawing address:
* ad = O7NYCFUL5XIJTYE3O4MKGMGMTN6ATQAJ

* puk1 = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE90U9sMxra8wxIaIBy87p09aM8n4r
* puk2 = Ke1eZOtL0Im19ItIIzT3AiKE0dRsHemcn5bUcSqnC/jC+3H8vaCtjn9ylg==

* s1 = MEQCIA3df2YnWjDVlNoq+vQlSLRDhH+ESeaIWnMUHfoC/G6L
* s2 = AiAA+FUe6DaLG8h0ilGagyq2zb+z71ZWUx3fpikeq+DU2Q==

Optionnaly:
* asset = <asset name >
if the asset used to trigger the AA is not the one stored.
  
Initial AA adress : 
Check in explorer: https://testnetexplorer.obyte.org/#fWsV0XKLBq4jZXjIDycprAgNfA1XqfZTTOLjXAa6guc=
Agent address: HUIPCMM7OCHJJA64GS56VRXYPULCUIYT
