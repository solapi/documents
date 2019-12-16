# 이벤트 목록 조회

## Request

```text
GET https://api.solapi.com/webhook/v1/events
```

등록된 이벤트 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `webhook:read` | `role-webhook:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| name | `string` |  | eq | 이름 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |

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
            "eventId": "WH01ET191031095607673x4KPmKzmvyI",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673sNa2FPUk7rz",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673osvtjyPWoIm",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673oUgJuUhvJjy",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673nwvsXzx70uM",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673n2G7sQocHPW",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673kOd3GdiZrOC",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673hoiGYItBwFR",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673eiN8uAfRATB",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673cP2LMhEtCsi",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673WgNLvtKYKZj",
            "name": "CashReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673WHfB8byubGL",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673UrGhFfR5IQT",
            "name": "CashReport",
            "dateCreated": "2019-10-31T09:56:07.701Z",
            "dateUpdated": "2019-10-31T09:56:07.701Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673SNrevqPphJ8",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673P86fsnFGTpq",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673NOALoPzx0Um",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.700Z",
            "dateUpdated": "2019-10-31T09:56:07.700Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673NEsqpelFgRM",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673Mqz1xmPb1MF",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673MjFQa1fGomb",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.685Z",
            "dateUpdated": "2019-10-31T09:56:07.685Z"
        },
        {
            "description": null,
            "eventId": "WH01ET191031095607673M6toswBP4Nu",
            "name": "MessageReport",
            "dateCreated": "2019-10-31T09:56:07.686Z",
            "dateUpdated": "2019-10-31T09:56:07.686Z"
        }
    ],
    "startKey": "WH01ET191031095607673x4KPmKzmvyI",
    "nextKey": "WH01ET191031095607673G8QZrG4Wnsf"
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

> 문서 생성일 : 2019-10-31

