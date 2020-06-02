# Signature

Signatures are calculated using <b>HMAC SHA3-384</b>.<br>
Use document specified content as input data, your Secret Key as key.<br>
The hash calculation results should be expressed as a hexadecimal string, which is the signature and case insensitive.

## PHP Example

Requires PHP 7.1.0 or later.

``` 
<?php

$secret_key = 'r9WzuQReIELAkDhG6gBjpyldUmxV2sHP3Yt8FONqCbfnTX7cS05ZoMiK1awJv4';

$uri = '/v1/invoice/create?ts=' . time() . '&nonce=' . md5(random_bytes(16));

/** @var string $sign the signature */
$sign = hash_hmac('SHA3-384', $uri, $secret_key);
echo $sign;
```

## Python Example

Requires Python 3.x

```
import time
import string
import random
import hashlib
import hmac

secret_key = b'r9WzuQReIELAkDhG6gBjpyldUmxV2sHP3Yt8FONqCbfnTX7cS05ZoMiK1awJv4'

uri = bytes('/v1/invoice/create?ts=' + str(int(time.time())) + '&nonce=' + ''.join([random.choice(string.ascii_letters+string.digits) for i in range(16)]), encoding = 'utf8')

m = hmac.new(secret_key, uri, hashlib.sha3_384)
sign = m.hexdigest()
print(sign)
```

