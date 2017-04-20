# Query


## JSON: 

```javascript
{
      "page_number": 1,
      "objecttype": 1,
      "page_size":100,
      "query":"(statuscode = 1)",    //optional field
      "fields":"accountid",    //optional field
      "sort_by":"createdon",    //optional field
      "sort_type":"desc" //optional field
}
```

## PHP:

```php
$data = '{
      "page_number": 1,
      "objecttype": 1,
      "page_size":100,
      "query":"(statuscode = 1)",    //optional field
      "fields":"accountid",    //optional field
      "sort_by":"createdon",    //optional field
      "sort_type":"desc" //optional field
        }';
$url='https://app.breezz.io/api/query'
$data_string = json_encode($data);  
$curl = curl_init();
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "POST");
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string);                                                                   
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(                                                                          
    'Content-Type: application/json',
    'tokenid: 0588209E-2715-419F-A913-732123456',                                                                                
    'Content-Length: ' . strlen($data_string))                                                                       
); 
$result = curl_exec($curl);
curl_close($curl);

```

## python:

```python
import requests
import json

url = 'https://app.breezz.io/api/query'
token_id = '73994acf-cd16-48bd-b8e1-1123456'

data = {
   “page_number": 1,
    "objecttype" : 1,
    "page_size" : 100,
    "query" :“(id = 123)"    #optional field
    “fields”: ”id”,    #optional field
    "sort_by": “createdon”,    #optional field
    “sort_type”: ”desc”, #optional field
}

headers = {'Content-type': 'application/json', 'tokenId': token_id, 'utc_time' : str(1)}
response = requests.post(url + "/api/query", data=json.dumps(data), headers=headers)
return json.loads(response.content)['data']
```

## ASP.net:

```c#
using System.Collections.Specialized;
using System.Net;
using System.Web.Script.Serialization;
using System.IO;

using (WebClient client = new WebClient())
            {
                string tokenid = "0588209E-2715-419F-7777-732123456"; 
                client.Headers.Set("tokenId", tokenid);
                client.Headers.Set("ContentType", "application/json");
                client.Headers.Set("utc_time", "1");
                client.Encoding = System.Text.Encoding.UTF8;
                string json = new JavaScriptSerializer().Serialize(new
                {
                    page_number = 1,
                    objecttype = 1,
                    page_size = 100,
                    query = "(statuscode = 1)",    //optional field
                    fields = "accountid",    //optional field
                    sort_by = "createdon",    //optional field
                    sort_type = "desc" //optional field
                });
                string result = client.UploadString("https://app.breezz.io/api/query", "POST", json);
            }
```
