---
sidebar_position: 3
---

# Security

In order to ensure the API security, query signature generated with the help of the secret key is used. Query signature is validated on our server and in case it doesn’t match, the error is returned.

### Generating query signature

Steps to generate query signature:

1. Gather the ALL parameters (query parameters, path parameters, form parameters) into associative array
2. If a JSON string is passed, decode it into an associative array and merge it with the rest of the query parameters
3. Stringify associative array
4. Get hash of the string using __SHA256__ algorithm and your __SECRET_KEY__

In the end you get the signature that can be used in queries.

Sample of signature generation on JavaScript (TypeScript) language:

```
import * as CryptoJS from "crypto-js";

function generateSignature(message: string, privateKey: string): string {
    const signature = CryptoJS.HmacSHA256(message, privateKey);
    
    return signature.toString(CryptoJS.enc.Hex);
}
```