# Deserializing
Depending on the byte prefix the device, the ledger is set to deserialize in the following ways

## UTF8 Message
> Byte prefix `0x01` (mainnet) or `0x0B` (testnet)

The payload must contain valid UTF8 bytes form byte range [1..]

## Digest Hash
> Byte prefix `0x03`

The payload must be 33 bytes exactly with the first byte being `0x03`

## Transaction Payload
> Byte prefix `0x02` (mainnet) or `0x0C` (testnet)


### Transaction must be formatted as follows:
#### Inner
> 24 bytes following the transaction type prefix

|Byte Range|Value|
--- | ---|
|0..8|nonce|
|8..16|validTo (date transaction is no expires|
|16..24|fee|

#### Header
> 25 bytes following the `Inner`

|Byte Range|Value|
--- | ---|
|0..21|contract|
|21..25|payload length|

#### Transaction Payload
> unknown bytes following the `Header`

|Byte Range|Value|
--- | ---|
|0..|transaction payload|

### Transaction MPC Transfer
There is a special check to see if the user is making a MPC transfer.  If they are a more custom deserialization occurs and a more detailed display on the Ledger device is provided

### Transaction Contract
For all other transactions, simply the Contract, fee, and payload are displayed

