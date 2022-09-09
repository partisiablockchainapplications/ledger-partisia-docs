# Ledger Application Code in C++

### Ledger Application
* Source code forks off the ledger-boilerplate project
   * [Source Code](https://gitlab.com/partisiablockchainapplications/ledger-app/-/tree/partisia)
* binary build
   * [app.apdu](./assets/bin/app.apdu)
   * [app.elf](./assets/bin/app.elf)
   * [app.hex](./assets/bin/app.hex)
   * [app.sha256](./assets/bin/app.sha256)

### Source Code Explained
All Ledger transports must be sent with a byte prefix that defined what the payload type is.  This is used to deserialize and display on the ledger device.

|Byte_Prefix|Enum|Description|
--- | --- | ---|
|0x01|SIGN_UTF8|Sign UTF8 message for Mainnet|
|0x02|SIGN_TRANSACTION|Sign Transaction for Mainnet|
|0x03|SIGN_DIGEST|Sign the exact bytes provided in payload.  Must be exactly 32 bytes like a sha256 hash|
|0x0B|SIGN_UTF8_TESTNET|Sign UTF8 message for Testnet|
|0x0C|SIGN_TRANSACTION_TESTNET|Sign Transaction for Testnet|

Please see for more information how Partisia Blockchain works:
* [Address](./address.md)
* [Transactions](./transactions.md)
* [Deserializing](./deserializing.md)
