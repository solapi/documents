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
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238srawfRTH61w",
            "eventId": "WH01ET191026212736238D9zPvZsYC2O",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238qtwVhHobYSb",
            "eventId": "WH01ET191026212736238Tnt8V6cov9T",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238mkhxQ5XsVO0",
            "eventId": "WH01ET191026212736238HA4Dz9Gja9F",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238bk5fIuJTyXt",
            "eventId": "WH01ET191026212736238FiHBZhMQSoX",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238bhgJ8Zw48Lf",
            "eventId": "WH01ET191026212736238o7SxBoMlacN",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238ZkBCl70D0H3",
            "eventId": "WH01ET191026212736238BxSRmcNkMJe",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238PHyQ7TSegrC",
            "eventId": "WH01ET191026212736238yndmdPtag5p",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238KcEn74tf8mI",
            "eventId": "WH01ET191026212736238ZR7ZQ6OpvuL",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736238707CjhwEQRq",
            "eventId": "WH01ET191026212736238nmYDHCKRyaY",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237x2dkTYgkB3d",
            "eventId": "WH01ET191026212736237hZuxM6xjstr",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237vdSnbIJOqzT",
            "eventId": "WH01ET1910262127362376EXefqVGtJR",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237vLCAPIr5fTG",
            "eventId": "WH01ET191026212736237aAa36zJPThs",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237sD2idsGSo2q",
            "eventId": "WH01ET191026212736238nYASqNTWVrI",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.259Z",
            "dateUpdated": "2019-10-26T20:27:36.259Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237g4V2haiADdX",
            "eventId": "WH01ET191026212736237MtakzFozG0L",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237foaNgKL2Egg",
            "eventId": "WH01ET191026212736237B9L85gRUoUa",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237aibGYfXDkzk",
            "eventId": "WH01ET191026212736237jojj2IRJgfb",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237aJ87pQ7dHE5",
            "eventId": "WH01ET191026212736237JfmtC52UWOb",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237D2DJio08A2k",
            "eventId": "WH01ET191026212736237RxjNqSL4sF7",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736237BcYly2lTPQl",
            "eventId": "WH01ET191026212736237wS3RuXgAutt",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.258Z",
            "dateUpdated": "2019-10-26T20:27:36.258Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191026212736236daWsrDMK7SA",
            "eventId": "WH01ET191026212736236pxyOqEvYikO",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-26T20:27:36.257Z",
            "dateUpdated": "2019-10-26T20:27:36.257Z"
        }
    ],
    "startKey": "WH01WH191026212736238srawfRTH61w",
    "nextKey": "WH01WH191026212736236d2yvNXifymW"
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

> 문서 생성일 : 2019-10-26

