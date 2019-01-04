# crypto-js-test
crypto-js example of test

## Node.js(Install)

```
npm install crypto-js
```

## Usage

This is just an example for use AES. [API](https://code.google.com/p/crypto-js)

***Quick Start***

```js
import CryptoJS from 'crypto-js'

// Encrypt
var ciphertext = CryptoJS.AES.encrypt('my message', 'secret key 123').toString();

// Decrypt
var bytes  = CryptoJS.AES.decrypt(ciphertext, 'secret key 123');
var originalText = bytes.toString(CryptoJS.enc.Utf8);

console.log(originalText); // 'my message'
```

### AES Encryption

```js
function Encrypt (data) {
  let srcs = ''
  if (typeof data === 'string') {
    srcs = CryptoJS.enc.Utf8.parse(data)
  } else if (typeof data === 'object') {
    srcs = CryptoJS.enc.Utf8.parse(JSON.stringify(data))
  }

  const encrypted = CryptoJS.AES.encrypt(srcs, key, {mode: CryptoJS.mode.CBC, padding: CryptoJS.pad.Pkcs7})
  return encrypted.toString()
}
```

### AES Decryption

```js
function Decrypt (data) {
  const decrypted = CryptoJS.AES.decrypt(data, key, {mode: CryptoJS.mode.CBC, padding: CryptoJS.pad.Pkcs7})

  console.log('decrypted: ' + decrypted.toString(CryptoJS.enc.Utf8))
  return decrypted.toString(CryptoJS.enc.Utf8)
}
```

## Reference

1. http://cryptojs.altervista.org/index.html
2. https://www.npmjs.com/package/crypto-js

##Online Tools

1. http://tool.oschina.net/encrypt/