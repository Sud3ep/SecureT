<!-- > SecureT is an API that generates unpredictable passwords using quantum randomness, preventing brute-force attacks. -->
[SecureT](https://securet.onrender.com/docs) is an API that generates unpredictable passwords using quantum randomness, preventing brute-force attacks. Unlike traditional password generators that use pseudo-random algorithms, the Quantum Password Generator API harnesses real quantum randomness to create unpredictable passwords. It also includes rate-limiting to prevent abuse.

Most password generators rely on:

• Algorithms (like random() or UUID) – These are deterministic and can be reverse-engineered.

• Seed-based randomness – Given the same seed, they produce the same results.

• Low entropy – They still follow mathematical patterns that hackers can exploit.


SecureT, on the other hand:

• Uses real quantum mechanics – Powered by LfD’s IDQ PCle, leveraging quantum vacuum fluctuations and true randomness.

• Unpredictable passwords – No algorithmic patterns, making it impossible to replicate.

• Stronger cryptographic security – Ideal for high-security systems, blockchain wallets, and encryption keys.

---

For easy testing, visit:
https://securet.onrender.com/docs


## Query Parameters

### length

Type: `Integer (int)`

Default: `12`

Allowed Values: `6 to 32`

#

### character_set

Type: `String (str)`

Default: `Composite`

Allowed Values:

`Alphanumeric` → Only letters (A-Z, a-z) and numbers (0-9)

`Symbols` → Only special characters (!@#$%^&*(), etc.)

`Composite` → Mix of letters, numbers, and symbols.

---

## API Usage

### cURL

Request:

```bash
curl -X 'GET' \
  'https://securet.onrender.com/create-password?length=16&character_set=Composite' \
  -H 'accept: application/json'
```

Response:

```js
{
  "password": "A&8sD!7f@K9$Hq*Y",
  "source": "https://lfdr.de",
  "explanation": "This password is generated using quantum vacuum fluctuations."
}
```
#

### Python

To use SecureT in a Python script, you can send a `GET` request using the requests library and handle the response as follows:

```python
import requests

# API endpoint and parameters
url = 'https://securet.onrender.com/create-password'
params = {
    'length': 16,
    'character_set': 'Composite'
}

response = requests.get(url, params=params)

if response.status_code == 200:
    data = response.json()
    print(f"Generated Password: {data['password']}")
else:
    print(f"Error: {response.status_code} - {response.text}")
```
#
### JavaScript

To use SecureT in a JavaScript, you can use fetch API to send a request:

Using fetch:

```js
const url = 'https://securet.onrender.com/create-password?length=16&character_set=Composite';

fetch(url)
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    return response.json();
  })
  .then(data => {
    console.log(`Generated Password: ${data.password}`);
  })
  .catch(error => {
    console.error(`Error: ${error.message}`);
  });

```

Using axios:

```js
const axios = require('axios');

const url = 'https://securet.onrender.com/create-password';
const params = {
  length: 16,
  character_set: 'Composite'
};

axios.get(url, { params })
  .then(response => {
    console.log(`Generated Password: ${response.data.password}`);
  })
  .catch(error => {
    console.error(`Error: ${error.response ? error.response.status : error.message}`);
  });

```

---



## Sources

- Quantum randomness provided by [LfD's IDQ PCle](https://lfdr.de), using quantum vacuum fluctuations for true random number generation.
---
