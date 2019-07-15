### btctxstore
---
https://github.com/F483/btctxstore

```sh
pip install btctxstore
export PYCOIN_NATIVE=openssl
```

```py
import binascii
from btctxstore import BtcTxStore

wifs = ["xxx"]

api = BtcTxStore(tetnet=True, dryrun=True)

data = binascii.hexlify(b"github.com/F483/btctxstore")
txid = api.store_nulldata(data, wifs)
print(txid)

// retrieve_nulldata.py
from btctxstore import BtcTxStore

api = BtcTxStore(testnet=True, dryrun=True)
txid = "xxx"
hexnulldata = api.retrieve_nulldata(txid)
print(hexnulldata)

// signverify.py
import binascii
from btctxstore import BtcTxStore

api = BtcTxStore(testnet=True, dryrun=True)
wif = api.create_key()
address = api.get_address(wif)
data = binascii.hexlify(b"messagetext")

signature = api.sign_data(wif, data)
print("signature:", signature)

isvalid = api.verify_signature(address, signature, data)
print("valid signature" if isvalid else "isvalid signature")

// split_utxos.py
from btctxstore import BtcTxStore

wif = "xxx"

api = BtcTxStore(testnet=True, dryrun=True)

limit = 100000000
txisd = api.split_utxos(wif, limit)
print(txids)
```

```
```


