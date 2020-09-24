# 이벤트 목록 조회

## Request

```text
GET https://api.solapi.com/webhook/v1/events
```

등록된 이벤트 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `webhook:read` | `role-webhook:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| name | `string` |  | eq | 이름 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최근 수정 날짜 |

## Samples

### readEvent.spec.js

> **Sample Request**

```text
http://api.solapi.com/webhook/v1/events?
```

> **Sample Response**

```javascript
{
    "limit": 20,
    "eventList": [
        {
            "description": null,
            "eventId": "WH01ET191230002851650zyiotTHQnAX",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650we54CuSEyrZ",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650wKciJhiO2Bf",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.658Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650ve9viyd1bu3",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650uYavsHiWjx1",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650uQylG7BRkvn",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650tqwGBls5vk8",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650tQkrqkNttvR",
            "name": "CashReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650s2Mzqi1DRsm",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650lbT6WuIIKeN",
            "name": "CashReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650kXzxaS8KB7U",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.658Z",
            "dateUpdated": "2019-12-30T00:28:51.658Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650iMikLyy8P2X",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650gXSiEL5tnDi",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650eCeZ6fA4UBz",
            "name": "CashReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650QPzROM6FZ28",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650Q4pplOpSEMk",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650Kc3hAPkHtgS",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.658Z",
            "dateUpdated": "2019-12-30T00:28:51.658Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650GXDJoE7pIuU",
            "name": "CashReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191230002851650FDC4GPbjDhy",
            "name": "MessageReport",
            "dateCreated": "2019-12-30T00:28:51.659Z",
            "dateUpdated": "2019-12-30T00:28:51.659Z"
        },
        {
            "description": null,
            "eventId": "WH01ET1912300028516507P3PIDi6k5a",
            "name": "CashReport",
            "dateCreated": "2019-12-30T00:28:51.660Z",
            "dateUpdated": "2019-12-30T00:28:51.660Z"
        }
    ],
    "startKey": "WH01ET191230002851650zyiotTHQnAX",
    "nextKey": "WH01ET1912300028516504c3aLJ4B43H"
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
  url: 'http://api.solapi.com/webhook/v1/events?'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/webhook/v1/events?";

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

url = "http://api.solapi.com/webhook/v1/events?"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X GET \
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    http://api.solapi.com/webhook/v1/events?
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/webhook/v1/events?")

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
  uri := "http://api.solapi.com/webhook/v1/events?"

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
    String targetUrl = "http://api.solapi.com/webhook/v1/events?";

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

> 문서 생성일 : 2019-12-30

