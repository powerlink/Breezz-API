# Create

## JSON: 

```javascript
{
 "accountname" : "IBM",
 "telephone1" : "442080687145",
 "idnumber" : "1234",
 "billingcity" : "London"
}
```

## PHP:

```php
$data = '{
       "accountname" : "IBM",
      "telephone1" : "442080687145",
      "idnumber" : "1234",
      "billingcity" : "London"
        }';
$url='https://app.breezz.io/api/record/account'
$data_string = json_encode($data);  
$curl = curl_init();
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "POST");
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string);                                                                   
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(                                                                          
    'Content-Type: application/json',
    'tokenid: 0588209E-2715-419F-A913-732D1234',                                                                                
    'Content-Length: ' . strlen($data_string))                                                                       
); 
$result = curl_exec($curl);
curl_close($curl);
```

## python:

```python
import requests
import json

data = {
      "accountname" : "IBM",
     "telephone1" : "442080687145",
     "idnumber" : "1234",
     "billingcity" : "London"
}

url = 'https://app.breezz.io/api/record/account'
token_id = '73994acf-cd16-48bd-b8e1-17bc8f'
headers = {'Content-type': 'application/json', 'tokenId': token_id}
response = requests.post(url, data=str(data), headers=headers)
return json.loads(response.content)['data']['Record']
```

## ASP.net:

```c#
using System.Collections.Specialized;
using System.Net;
using System.Web.Script.Serialization;
using System.IO;

using (WebClient client = new WebClient())
            {
                string tokenid = "0588209E-2715-419F-1237-7312345"; 
                client.Headers.Set("tokenId", tokenid);
                client.Encoding = System.Text.Encoding.UTF8;
                string json = new JavaScriptSerializer().Serialize(new
                {
                    accountname = "IBM",
                    telephone1 = "442080687145",
                    idnumber = "1234",
                    billingcity = "London"
                });
                string result = client.UploadString("https://app.breezz.io/api/record/account", "POST", json);
            }
```
