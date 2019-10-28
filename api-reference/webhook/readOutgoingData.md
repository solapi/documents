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
            "webhookId": "WH01WH191028182136846BFMwlMo1DXa",
            "eventId": "WH01ET191028182136846KhHNyUgz5cP",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845yLwus9lINN5",
            "eventId": "WH01ET191028182136845z4rGZJf1f3M",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845xMqcaywQbJx",
            "eventId": "WH01ET191028182136845MnTUaAVpnPo",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845x9cLZzuVJq1",
            "eventId": "WH01ET191028182136845R9qFqvQIqAn",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845wFc86I58sj1",
            "eventId": "WH01ET1910281821368453Z6e205Sbb4",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845rySU0DK9eFb",
            "eventId": "WH01ET191028182136845rgbHnRdnhXH",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845ioVkN0celyG",
            "eventId": "WH01ET191028182136845EkhUMn0rxzt",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845g1X2rr3cQXp",
            "eventId": "WH01ET191028182136845DpU6MmjsGYY",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845a97BC02zEjg",
            "eventId": "WH01ET191028182136845NuaAw1FeLjQ",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845WRdXqKyFD7d",
            "eventId": "WH01ET191028182136845co5xwGMd9m2",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845L4m7ShmwWZN",
            "eventId": "WH01ET191028182136845E3Rs26m5ogN",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136845FJG5A0tnfIS",
            "eventId": "WH01ET191028182136846hqnfpY18bvL",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910281821368459rm8WwKYP2o",
            "eventId": "WH01ET191028182136845T1rwZt6waf9",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910281821368458ZOobor8Gdw",
            "eventId": "WH01ET191028182136845NYmiW6IpcYI",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.866Z",
            "dateUpdated": "2019-10-28T18:21:36.866Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844z55H03sredv",
            "eventId": "WH01ET191028182136844I7moOi8qzHG",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844czRjKpW0VUB",
            "eventId": "WH01ET191028182136844lEqNiX91EVE",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844av1z0QU512i",
            "eventId": "WH01ET191028182136844kIdeGwIlko2",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844Y9nECi9XVrG",
            "eventId": "WH01ET191028182136844QqTUHCIw9Jc",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.864Z",
            "dateUpdated": "2019-10-28T18:21:36.864Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844Uwz1Mv8vWYr",
            "eventId": "WH01ET191028182136844wgngjZOT8Oq",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.865Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191028182136844S6rU80k5bWI",
            "eventId": "WH01ET191028182136844xt3NpkUFwd0",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-28T18:21:36.864Z",
            "dateUpdated": "2019-10-28T18:21:36.865Z"
        }
    ],
    "startKey": "WH01WH191028182136846BFMwlMo1DXa",
    "nextKey": "WH01WH191028182136844H3KknebPyCY"
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

> 문서 생성일 : 2019-10-28

