# 웹훅 수정

## Request

```text
PUT https://api.solapi.com/webhook/v1/outgoing/:webhookId
```

등록된 웹훅을 수정합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `webhook:write` | `role-webhook:write` | `ACTIVE` | `ACTIVE` | O |

### 2차 인증 필요

| ARS 전화 인증 | 이메일 OTP |
| :---: | :---: |
|  |  |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :webhookId | 설명 없음 |

### Request Structure

```javascript
{
    "eventId": "string",
    "url": "string",
    "secret": "string",
    "status": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| eventId | `string` |  | 설명 없음 |
| url | `string` |  | 설명 없음 |
| secret | `string` |  | 설명 없음 |
| status | `string` |  | 상태값 |

## Samples

### updateOutgoingData.spec.js

> **Sample Request**

```javascript
{
    "eventId": "WH01ET191230002851190wQcCSqNEIMz",
    "url": "https://solapi.com/report1",
    "secret": "secretKey",
    "status": "INACTIVE"
}
```

> **Sample Response**

```javascript
{
    "secret": "ee1b507610b2d8c366ece22a8d89c6487c710db5",
    "status": "INACTIVE",
    "failCount": 0,
    "accountId": "12925149",
    "webhookId": "WH01WH191230002851190nhxjcDhWZJE",
    "eventId": "WH01ET191230002851190wQcCSqNEIMz",
    "url": "https://solapi.com/report1",
    "dateCreated": "2019-12-30T00:28:51.614Z",
    "dateUpdated": "2019-12-30T00:28:51.621Z"
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    eventId: 'WH01ET191230002851190wQcCSq...',
    url: 'https://solapi.com/report1',
    secret: 'secretKey',
    status: 'INACTIVE'
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE'
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
$url = "http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE";
$data = '{"eventId":"WH01ET191230002851190wQcCSq...","url":"https://solapi.com/report1","secret":"secretKey","status":"INACTIVE"}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
        'content' => $data,
        'method'  => 'PUT'
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

url = "http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"eventId":"WH01ET191230002851190wQcCSq...","url":"https://solapi.com/report1","secret":"secretKey","status":"INACTIVE"}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X PUT \
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    -H 'Content-Type: application/json' \
    -d '{"eventId":"WH01ET191230002851190wQcCSq...","url":"https://solapi.com/report1","secret":"secretKey","status":"INACTIVE"}' \
    http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "eventId": "WH01ET191230002851190wQcCSq...",
  "url": "https://solapi.com/report1",
  "secret": "secretKey",
  "status": "INACTIVE"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Put.new(uri.request_uri, headers)
request.body = data.to_json

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
  uri := "http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE"
  data := strings.NewReader(`{"eventId":"WH01ET191230002851190wQcCSq...","url":"https://solapi.com/report1","secret":"secretKey","status":"INACTIVE"}`)

  req, err := http.NewRequest("PUT", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")
  req.Header.Set("Content-Type", "application/json")

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
    String targetUrl = "http://api.solapi.com/webhook/v1/outgoing/WH01WH191230002851190nhxjcDhWZJE";
    String parameters = "{\"eventId\":\"WH01ET191230002851190wQcCSq...\",\"url\":\"https://solapi.com/report1\",\"secret\":\"secretKey\",\"status\":\"INACTIVE\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");
    con.setRequestProperty("Content-Type", "application/json");

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

