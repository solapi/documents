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
            "description": null,
            "eventId": "WH01ET191030195144219zU3xgGfAQf2",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219uNukZWGCRm4",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219peDDKMRFWHl",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.232Z",
            "dateUpdated": "2019-10-30T19:51:44.232Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219ox9xPOkMmJv",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.232Z",
            "dateUpdated": "2019-10-30T19:51:44.232Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219oVBDesVzh69",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219k38fXQDgjJQ",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219Xb5B65R2ked",
            "name": "CashReport",
            "dateCreated": "2019-10-30T19:51:44.234Z",
            "dateUpdated": "2019-10-30T19:51:44.234Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219XaTectabp31",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219OQmnQFk1WTi",
            "name": "CashReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144219HY92qDmK9WE",
            "name": "CashReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET1910301951442198QQ3qJhkPaf",
            "name": "CashReport",
            "dateCreated": "2019-10-30T19:51:44.234Z",
            "dateUpdated": "2019-10-30T19:51:44.234Z"
        },
        {
            "description": null,
            "eventId": "WH01ET1910301951442196HwjQukW3bi",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.232Z",
            "dateUpdated": "2019-10-30T19:51:44.232Z"
        },
        {
            "description": null,
            "eventId": "WH01ET1910301951442192AyLYQprcu0",
            "name": "CashReport",
            "dateCreated": "2019-10-30T19:51:44.233Z",
            "dateUpdated": "2019-10-30T19:51:44.233Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218v7D5jHX3VTL",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.227Z",
            "dateUpdated": "2019-10-30T19:51:44.227Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218tXpVQMBtbV4",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.227Z",
            "dateUpdated": "2019-10-30T19:51:44.227Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218nnfhGjiwMcO",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.227Z",
            "dateUpdated": "2019-10-30T19:51:44.227Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218l4udQTbzChV",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.227Z",
            "dateUpdated": "2019-10-30T19:51:44.227Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218iwb8YUELrwW",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.228Z",
            "dateUpdated": "2019-10-30T19:51:44.228Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218fCbGHe8I8nt",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.228Z",
            "dateUpdated": "2019-10-30T19:51:44.228Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191030195144218aemxT1g1soN",
            "name": "MessageReport",
            "dateCreated": "2019-10-30T19:51:44.227Z",
            "dateUpdated": "2019-10-30T19:51:44.227Z"
        }
    ],
    "startKey": "WH01ET191030195144219zU3xgGfAQf2",
    "nextKey": "WH01ET191030195144218a8AbluRPQxN"
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

> 문서 생성일 : 2019-10-30

