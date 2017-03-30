# Update

## JSON: 
<a href="">=> Download</a>

```javascript
{
 "accountname" : "jhon",
 "telephone1" : "036339060",
 "idnumber" : "1234",
 "billingcity" : "tel aviv"
}
```

## PHP:

```php

```

## python:

```python
import requests
import json

object_id = '12345cf-cd16-48bd-b8e1'
url = 'https://app.breezz.io/api/record/account/'
token_id = '73994acf-cd16-48bd-b8e1-17bc8f'
headers = {'Content-type': 'application/json', 'tokenId': token_id, 'utc_time' : str(1)}
response = requests.get(url + str(object_id), data=str(data), headers=headers)
return json.loads(response.content)['data']
```

## ASP.net:

```c#

```
