# yopass_api

This is a fork of the the project made [Sergey Ilyashevich](https://github.com/silyashevich), only compatible with Yopass v13.0.0 or later.

This is a module to work with a (the) [Yopass](https://github.com/jhaals/yopass) backend created by [Johan Haals](https://github.com/jhaals).
This module will allow you to use Python and self-hosted Yopass in automation projects.


## Basic Example

This is a basic example of store secret, get link and fetch secret:

```py
from yopass_api import Yopass

yopass = Yopass(api="https://api.yopass.se")
secret_password = yopass.generate_passphrase(length=5)
secret_id = yopass.store(
    message="test",
    password=secret_password,
    expiration="1w",
    one_time=False,
)
secret_url = yopass.secret_url(secret_id=secret_id, password=secret_password)
print(secret_url)
message = yopass.fetch(secret_id=secret_id, password=secret_password)
print(message)

```
