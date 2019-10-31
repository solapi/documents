# 웹훅 목록 조회

## Request
```
GET https://api.solapi.com/webhook/v1/outgoing
```

등록된 웹훅 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `webhook:read` | `role-webhook:read` | `ACTIVE` |  | O |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| url | `string` |  | eq | 설명 없음 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| status | `string` |  | eq | 상태값 |
| handleKey | `타입을 찾을 수 없음` |  | eq | 설명 없음 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |

---

## Samples

### readOutgoingData.spec.js

> **Sample Request**

```
http://api.solapi.com/webhook/v1/outgoing?
```

> **Sample Response**

```json
{
    "limit": 20,
    "webhookList": [
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017187U7l5hdPKecl",
            "eventId": "WH01ET191031070017187fDbNYAWqBz3",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017187FvJA3qLDTqs",
            "eventId": "WH01ET191031070017187GYFcdvFAnxz",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910310700171877iBd4cUOWwr",
            "eventId": "WH01ET191031070017187JYxwWYc2JKA",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186qvopRjMyUm0",
            "eventId": "WH01ET191031070017186EloHPiweWuf",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186itO4i6DmrNH",
            "eventId": "WH01ET1910310700171869t1rwLNoWtn",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186cefCu4zE0oq",
            "eventId": "WH01ET191031070017186lz3wSdWLE4q",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186VtJqOwjsn0q",
            "eventId": "WH01ET191031070017186XV7MgWQ3AbB",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186P7fBj0xtSnA",
            "eventId": "WH01ET191031070017186BlHAaq3AjN9",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186Gq5X41Zfhze",
            "eventId": "WH01ET191031070017186ncXzLZ1zjL0",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186FZgECZH4Pb7",
            "eventId": "WH01ET1910310700171864aFOKsVzEoZ",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186F8ryLYBek7c",
            "eventId": "WH01ET1910310700171868DL8GXF95DW",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186CJlZa1HjvSk",
            "eventId": "WH01ET191031070017187DcdzSBMTM7m",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-31T07:00:17.209Z",
            "dateUpdated": "2019-10-31T07:00:17.209Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186CBQkWqjbejR",
            "eventId": "WH01ET191031070017186hUcMjAhdUbb",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017186C8flrt2exsx",
            "eventId": "WH01ET191031070017186dWhrX676a1X",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910310700171864hLHRwW8GY6",
            "eventId": "WH01ET191031070017186ejmjjy6RiZo",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017185zs0GwDR7b36",
            "eventId": "WH01ET191031070017186SDK0Ln9dq8O",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017185kqG7L0RU2uZ",
            "eventId": "WH01ET191031070017185IzMxYoJoObm",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.207Z",
            "dateUpdated": "2019-10-31T07:00:17.207Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017185NLkaJ8rHeLA",
            "eventId": "WH01ET191031070017185GHAgfY6nfBb",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.206Z",
            "dateUpdated": "2019-10-31T07:00:17.207Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017185LXRMj5CzCHK",
            "eventId": "WH01ET191031070017185QagnYOn5JYp",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.207Z",
            "dateUpdated": "2019-10-31T07:00:17.207Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191031070017185GaH58QbVmek",
            "eventId": "WH01ET191031070017185xzP6ph9qCKK",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-31T07:00:17.208Z",
            "dateUpdated": "2019-10-31T07:00:17.208Z"
        }
    ],
    "startKey": "WH01WH191031070017187U7l5hdPKecl",
    "nextKey": "WH01WH1910310700171857QcRmB66wVK"
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/webhook/v1/outgoing?'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});

```
{% endtab %}

{% tab title="JQUERY" %}

```javascript
var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  url: 'http://api.solapi.com/webhook/v1/outgoing?'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/webhook/v1/outgoing?";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'GET'
    )
);

$context  = stream_context_create($options);
$result = file_get_contents($url, false, $context);

var_dump($result);

```
{% endtab %}

{% tab title="PYTHON" %}

```python
import requests

url = "http://api.solapi.com/webhook/v1/outgoing?"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/webhook/v1/outgoing?
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/webhook/v1/outgoing?")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, headers)

response = http.request(request)
puts response.code
puts response.body

```
{% endtab %}

{% tab title="GO" %}

```go
package main

import (
  "fmt"
  "io/ioutil"
  "net/http"
  "strings"
)

func main() {
  uri := "http://api.solapi.com/webhook/v1/outgoing?"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")

  client := &http.Client{}
  resp, err := client.Do(req)
  if err != nil { panic(err) }
  defer resp.Body.Close()

  bytes, _ := ioutil.ReadAll(resp.Body)
  str := string(bytes)
  fmt.Println(str)
}

```
{% endtab %}

{% tab title="JAVA" %}

```java
package solapi;

import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class Request {
  public static void main(String[] args) throws Exception {
    String targetUrl = "http://api.solapi.com/webhook/v1/outgoing?";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");

    con.setDoOutput(true);
    DataOutputStream wr = new DataOutputStream(con.getOutputStream());
    wr.writeBytes(parameters);
    wr.flush();
    wr.close();

    int responseCode = con.getResponseCode();
    BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
    String line;
    StringBuffer response = new StringBuffer();
    while ((line = in.readLine()) != null) {
      response.append(line);
    }
    in.close();

    System.out.println("HTTP response code : " + responseCode);
    System.out.println("HTTP body : " + response.toString());
  }
}

```
{% endtab %}

{% endtabs %}

---

> 문서 생성일 : 2019-10-31

