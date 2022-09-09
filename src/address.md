### Address Derived
Partisia HD addresses are derived as follows:
* Path `m/44'/3757'/0'/0/<idx>`
   > For Ledger `idx` will be 0
* The Private Key is derived from the HD Path, and the uncompressed Public Key is derived from the Private Key
* To keep compatibility we convert the 64 byte public key into 65 bytes by prefixing the public key with `0x04`
* A sha256 hash is generated from the 65 bytes Public Key
* The first 20 bytes of the hash prepended by `0x00` to create a 21 byte Partisia Address