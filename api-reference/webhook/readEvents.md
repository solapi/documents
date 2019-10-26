# 이벤트 목록 조회

## Request
```
GET https://api.solapi.com/webhook/v1/events
```

등록된 이벤트 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `webhook:read` | `role-webhook:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| name | `string` |  | eq | 이름 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |

---

## Samples

### readEvent.spec.js

> **Sample Request**

```
http://api.solapi.com/webhook/v1/events?
```

> **Sample Response**

```json
{
    "limit": 20,
    "eventList": [
        {
            "eventId": "WH01ET191026212736470r1Mss0acw5d",
            "name": "CashReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470pzMYCIJVhY3",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470fcU4b5RZkr0",
            "name": "CashReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470fVbQetEojd8",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470cMyn7p1WROK",
            "name": "CashReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470WxVL2rhx1UH",
            "name": "CashReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736470KiP8OvJPpvz",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET1910262127364708iq41iN7xrf",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET1910262127364705ssfDBl2RNf",
            "name": "CashReport",
            "dateCreated": "2019-10-26T20:27:36.479Z",
            "dateUpdated": "2019-10-26T20:27:36.479Z"
        },
        {
            "eventId": "WH01ET191026212736469sYWTIrhUx9p",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.476Z",
            "dateUpdated": "2019-10-26T20:27:36.476Z"
        },
        {
            "eventId": "WH01ET191026212736469r24rRzqYKHM",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.476Z",
            "dateUpdated": "2019-10-26T20:27:36.476Z"
        },
        {
            "eventId": "WH01ET191026212736469pfXLR7Ho9Fp",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.476Z",
            "dateUpdated": "2019-10-26T20:27:36.476Z"
        },
        {
            "eventId": "WH01ET191026212736469peapHYalVTY",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.477Z",
            "dateUpdated": "2019-10-26T20:27:36.477Z"
        },
        {
            "eventId": "WH01ET191026212736469nESEqiYHkxy",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.476Z",
            "dateUpdated": "2019-10-26T20:27:36.476Z"
        },
        {
            "eventId": "WH01ET191026212736469luSPbn8muGg",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.477Z",
            "dateUpdated": "2019-10-26T20:27:36.477Z"
        },
        {
            "eventId": "WH01ET191026212736469hRNZZViVGRj",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.478Z",
            "dateUpdated": "2019-10-26T20:27:36.478Z"
        },
        {
            "eventId": "WH01ET191026212736469gRPEX04H01R",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.478Z",
            "dateUpdated": "2019-10-26T20:27:36.478Z"
        },
        {
            "eventId": "WH01ET191026212736469eAXKPFyJYFT",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.478Z",
            "dateUpdated": "2019-10-26T20:27:36.478Z"
        },
        {
            "eventId": "WH01ET191026212736469bcbf6t3jq1D",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.476Z",
            "dateUpdated": "2019-10-26T20:27:36.476Z"
        },
        {
            "eventId": "WH01ET191026212736469b5sIXeeiGRz",
            "name": "MessageReport",
            "dateCreated": "2019-10-26T20:27:36.475Z",
            "dateUpdated": "2019-10-26T20:27:36.475Z"
        }
    ],
    "startKey": "WH01ET191026212736470r1Mss0acw5d",
    "nextKey": "WH01ET191026212736469ZyBSmvGBTYy"
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

{% tab title="JQUERY" %}

```javascript
var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  url: 'http://api.solapi.com/webhook/v1/events?'
};

$.ajax(options).done(function(response) {
  console.log(response);
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

```curl
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

---

> 문서 생성일 : 2019-10-26

