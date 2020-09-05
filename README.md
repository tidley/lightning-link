# lightning-link

Connecting BTC Lightning and IPFS for something magical

## Scenarios

### Scenario A: Data assurance for the receiver

#### Example 1:

Alice wants to receive some information (software program) from Bob. Alice trusts Bob but wants to be certain the code she will isn't malicious or outdated.

Alice can send Bob an encrypted message using the Lightning network requesting the information. Alice and Bob are certain of their identities since they are both using their trusted Lightning nodes.

Bob can return a message with the IPFS CID of the information contained within the appropriate field. Alice is able to retrieve the file from the IPFS network with confidence in the authenticity.

#### Example 2. Latest version of data

Bob can update Alice with the most recent CID strings at any time.

### Scenario B: Recipient guarantee for sender

#### Example 1:

Due to the encrypted messaging Bob can be assured it's Alice receiving this information instead of an unknown and untrusted party.

### Scenario C: Asset transfer in exchange for data

#### Example 1:

Bob can charge for the receipt of data and so Alice must send the required value before Bob returns the location of the information.

### Scenario D: Immutable contracts

#### Example 1: Parallel contract interaction

Alice and Bob can send updates via transactions to each other to notify of any changes in real time.
Alice and Bob want their services to be linked in real-time. Direct messaging 1032 bytes(???) allows for instantaneous updates but also a smart contract can exist with real-time parameter updates relayed between parties.

#### Example 2: Immutable state recording

Contract states can be frozen by using a message at any time. Hash of contract can be shared to prove state when last transaction occured. [message field... ]

#### Example 3: Multiparty contract engagement

The

### Scenario E: Data encryption

The message_hash can be generated prior to sending the message and so could be used to encrypt and store the data before sending a message out to the receiver.

### Scenario F: Monetisation of processing power

#### Example 1.

It allows nodes which hold and store contracts as IPFS CID's to offer running them for a fee, paid in sats by the requestor in the keysend invoice.

#### Example 2: Proving data ownership

Node can be requested to pin data for a recurring fee.

The payer can be certain the node still has the data by requesting some random bits back, of which the payer knows a small subset. To prove ownership of data the storing node must return the relevant data from the stored file. The payer will request a random set of data each time to be sure the storing node has the whole file.

### Summary

- Private
- Secure
- Cheap
- Quick

## Lightning Fields

E.g.: `lncli sendpayment --keysend --dest=031920d584984042b198a2a8e5d0608a7523bac56948939580a15b1fd3e4c98e2a --amt=1 --final_cltv_delta=40 --data 65537=$(echo -n "QmdgWDsRBhij7jKB7GEtSeHcjVU2ZDB7jm5VzYRSkjFL4G" | xxd -pu -c 10000)`

| Field   | Use case         | Example                                                                          |
| ------- | ---------------- | -------------------------------------------------------------------------------- |
| 65537   | Hash of contract | `7629168=`dollarSign\*`(echo -n "QmdgWDsRBhij7jKB7GEtSeHcjVU2ZDB7jm5VzYRSkjFL4G" | xxd -pu -c 10000)` |
| 7629168 | IPFS CID         | `7629168=`dollarSign\*`(echo -n "QmdgWDsRBhij7jKB7GEtSeHcjVU2ZDB7jm5VzYRSkjFL4G" | xxd -pu -c 10000)` |

\*VSCode wants to put a \ in front of \$ and \* when saving...
