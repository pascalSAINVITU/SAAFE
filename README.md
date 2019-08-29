# SAAFE
## Safe Autonomous Agent Forwarding Estate powered by Obyte

Inspired by the Bank with Secret of Obbie Barborico, this AA can safely store any public assets in a drawer of a safe. The assets can be as safely withdrawn from a drawer by anyone in possession of the private key associated to the public one used to stored the funds. The withdrawer needs to sign a message containing the wanted withdraw address. 

GitHub: https://github.com/pascalSAINVITU/SAAFE

## Use cases:
* It can be use for cold storage of any public assets.

## Flaw
* Unfortunately, public keys and signatures are too long for a single field, so they have to be introduce in several parts, puk1, puk2, (puk 3, puk 4), s1 and s2 (s3, s4).

## Additionnal features
* For safety reasons to validate the storage, the signature of a message composed of the word 'safe' must be provided to ensure that the key pair created is supported and avoid the funds to be stucked forever in the AA.
* If the drawer was set to private at its creation, only the creator can withdraw the funds. This option allows a drawer to be managed exclusively from an another AA.
* For replay protection, the withdraw signature cannot be used 2 times in a row.
* SAAFE is using DANAA (Dynamic Asset Names AA) to get registered assets short names.

## Example of workflow:

### You want to create a drawer, you need a pair of keys:
* public key = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE8H5XU2SEpdbIhPUwP2EPdWkkBeqHfxlPW0GdTwBAMY2mMs/Hxz8T/ns79o9inWJ1F3VW5qn2UMtB74x4isZqOw==
* private key = MHQCAQEEICZ3gsnwe0cK5pxrjWYC+yry+iAIDpXIdbx6MygiBwMooAcGBSuBBAAKoUQDQgAE8H5XU2SEpdbIhPUwP2EPdWkkBeqHfxlPW0GdTwBAMY2mMs/Hxz8T/ns79o9inWJ1F3VW5qn2UMtB74x4isZqOw==

### To store funds, you need to sign the message 'safe':
'safe' signature = MEQCIE36nzWEmsuWbhtSqQnwM3npU0AfpNm9QBSThz1x4jP3AiBbYaMG/4yRJEu7OcKSXur1vvFGZSEjCVijYuOCWjv/xg==

You have to provide the following data:
   * 'puk1' = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE8H5XU2SEpdbIhPUwP2EPdWkkBeqHfxl      // a first part of the publi key
   * 'puk2' = PW0GdTwBAMY2mMs/Hxz8T/ns79o9inWJ1F3VW5qn2UMtB74x4isZqOw==			// the second part
   * 's1' = MEQCIE36nzWEmsuWbhtSqQnwM3npU0AfpNm9QBSThz1x4jP3 							// first part of the 'safe' signature
   * 's2' = AiBbYaMG/4yRJEu7OcKSXur1vvFGZSEjCVijYuOCWjv/xg==							// second part of the 'safe' signature

Optionnally set the drawer to private so that only the creator can trigger a withdraw:
   * 'private' = true

### To withdraw to 35IT3ZYKEPQSCXG2F7A7KWNRAD3SZXN4 you need to sign a message containing this address:
'35IT3ZYKEPQSCXG2F7A7KWNRAD3SZXN4' signature = MEUCIQDm3WwTiryA24f+dlXvMhNYhg6yJWhqw/nx1mcIxQuzpwIgf1wuhehvt5+f4z2oPapZHxOo+F5txkqYCA20ujpklYY=

You have to provide the following data:
   * 'puk1' = MFYwEAYHKoZIzj0CAQYFK4EEAAoDQgAE8H5XU2SEpdbIhPUwP2EPdWkkBeqHfxl      // a first part of the publi key
   * 'puk2' = PW0GdTwBAMY2mMs/Hxz8T/ns79o9inWJ1F3VW5qn2UMtB74x4isZqOw==			// the second part
   * 's1' = MEUCIQDm3WwTiryA24f+dlXvMhNYhg6yJWhqw/nx1mcIxQuzpwIgf1 			// first part of the '<withdraw_address>' signature
   * 's2' = wuhehvt5+f4z2oPapZHxOo+F5txkqYCA20ujpklYY=				// second part of the '<withdraw_address>' signature
   * 'withdraw_address' = 35IT3ZYKEPQSCXG2F7A7KWNRAD3SZXN4					// Withdraw address must be the one signed

Optionnaly:
   * 'asset' = < asset id >
if the asset used to trigger the AA is not the one stored.
   * 'withdraw_amount' = <amount>
if you don't want to withdraw the full balance

## States description:
### storage drawers
* drawer_<hash> = store the balance for a given puk and asset, <hash> is the sha256 of puk and asset;
* last_s_<puk> = store the last signature (part1) used with the puk, to avoid Harry to replay the withdraw; 
