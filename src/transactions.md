### Transactions Explained
In Partisia blockchain a valid transaction signature is defined by the following steps:
* A Chain Id is appended to the end of a transaction payload
   > Chain Id for Testnet is fixed at: [0, 0, 0, 27, 80, 97, 114, 116, 105, 115, 105, 97, 32, 66, 108, 111, 99, 107, 99, 104, 97, 105, 110, 32, 84, 101, 115, 116, 110, 101, 116]
   > Chain Id for Mainnet is fixed at: [0, 0, 0, 19, 80, 97, 114, 116, 105, 115, 105, 97, 32, 66, 108, 111, 99, 107, 99, 104, 97, 105, 110]
* A sha256 hash is then generated from The transaction payload.  This 32 byte hash is called the `digest`
* The private key is used to generate a canonical signature from the `digest`
* The Signature returned from the Ledger Device is in `DER` format.  The `ledger-mpc-app` converts it into Partisia Signature format below.

### Partisia Signatures
Partisia Signature are always 65 bytes and defined as follows:

|Byte Range|Value|
--- | ---|
|0..1|Recovery Param|
|1..33|R Value|
|33..65|S Value|
