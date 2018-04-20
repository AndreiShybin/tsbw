## The Simplest Bitcoin Wallet

**The following Bitcoin folks are implemented**
Bitcore (BTX): https://bitcore.cc/tsbw/btx/
Bitcoin (BTC): https://bitcore.cc/tsbw/
Bitcoin Cash (BTC): https://bitcore.cc/tsbw/bcc/


Nothing is sent to a server, everything is done in the browser. It gets utxo and sends signed txs via external API's.

All API access is wrapped in a "backend" object, which can be easily swapped. 
- for Bitcore (BTX): insight.bitcore.cc
- for Bitcoin (BTC): blochchain.info
- for Bitcoin Cash (BTC): blockexplorer.com

You can enter a compressed or uncompressed WIF key as your passphrase; this means you can use the same wallets you have at https://coinb.in or any other wallet that allows exporting in this format.

----

The code is based on [coinb.in](https://github.com/OutCast3k/coinbin), forked form [tsbw.io](https://github.com/NxtChg/tsbw) (see https://tsbw.io) and BTX support was been added.

It's also a good start if you are interested to learn about Bitcoin and JS wallets since it's a lot simpler than the original.

Usage example:
```
var tx = btc.new_tx();

tx.add_input ('01020304abcdef', 0, '76a9141d8f0476ea05d9459e004fd0ff10588dd3979e6788ac'); // txid, no, script
tx.add_output('13nwZVh9RsKuZGegVn5KWHM51dA98Mho5f', 1234); // address, amount

var keys = btc.get_keys('123'); // 123 = passphrase

var signed = tx.sign(keys); console.log(signed);
```
