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
            "eventId": "WH01ET191028182137154BES3JspIqMZ",
            "name": "CashReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET1910281821371546iCdIMJE8je",
            "name": "CashReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153ycHbOyKKazq",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.161Z",
            "dateUpdated": "2019-10-28T18:21:37.161Z"
        },
        {
            "eventId": "WH01ET191028182137153y1SXnK7fTiJ",
            "name": "CashReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153uk1TFq3M7ob",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153udYwy498uLD",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153sudoPl2mhnK",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153q0rHIc5vjhi",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153ovrrJ9aiuHQ",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153lOpxJ6UhRcE",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153lNPK0pAnhxF",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153jsWUWKxccIh",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153j7vekdbVHPe",
            "name": "CashReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153iDaCvgjlIlE",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153fDGKJ59vC5f",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.161Z",
            "dateUpdated": "2019-10-28T18:21:37.161Z"
        },
        {
            "eventId": "WH01ET191028182137153fCCF4Q5xpdC",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.161Z",
            "dateUpdated": "2019-10-28T18:21:37.161Z"
        },
        {
            "eventId": "WH01ET191028182137153ds7mq6FvQiP",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.161Z",
            "dateUpdated": "2019-10-28T18:21:37.161Z"
        },
        {
            "eventId": "WH01ET191028182137153R6GTaqgKMKR",
            "name": "CashReport",
            "dateCreated": "2019-10-28T18:21:37.169Z",
            "dateUpdated": "2019-10-28T18:21:37.169Z"
        },
        {
            "eventId": "WH01ET191028182137153OmX5TvNEr2z",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        },
        {
            "eventId": "WH01ET191028182137153NvVoyzGhcqJ",
            "name": "MessageReport",
            "dateCreated": "2019-10-28T18:21:37.160Z",
            "dateUpdated": "2019-10-28T18:21:37.160Z"
        }
    ],
    "startKey": "WH01ET191028182137154BES3JspIqMZ",
    "nextKey": "WH01ET191028182137153NeQzdWQG3rC"
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

> 문서 생성일 : 2019-10-28

