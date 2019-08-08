# 앱 정보 업데이트

## Request

```text
PUT https://api.solapi.com/appstore/v2/me/apps/:appId
```

앱 정보를 업데이트 합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `appstore:write` | `role-appstore:write` | `ACTIVE` |  | O |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :appId | 앱 아이디 |

### Request Structure

```javascript
{
    "appName": "string",
    "appVersion": "string",
    "clientId": "string",
    "redirectUri": "string",
    "thumbnail": "string",
    "screenshots": [
        "string"
    ],
    "homepage": "string",
    "profit": {
        "sms": "number",
        "lms": "number",
        "mms": "number",
        "ata": "number",
        "cta": "number"
    },
    "categories": [
        "string"
    ],
    "intro": "string",
    "description": "string",
    "email": "email",
    "scope": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| appName | `string` |  | 앱 이름 |
| appVersion | `string` |  | 앱 버전 |
| clientId | `string` |  | 클라이언트 아이디 |
| redirectUri | `string` |  | 리다이렉트 URL |
| thumbnail | `string` |  | 미리보기 사진 \(썸네일\) |
| screenshots | `array` |  | 컨텐츠 이미지 |
| homepage | `string` |  | 홈페이지 주소\(링크\) |
| [profit](updateapp.md#body-profit) | `object` |  | 수익 |
| categories | `array` |  | 카테고리 |
| intro | `string` |  | 앱 소개 |
| description | `string` |  | 앱 설명 |
| email | `email` |  | 이메일 |
| scope | `string` |  | 필요 스코프 |

### Body / profit

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| sms | `number` | O | 단문 메시지 |
| lms | `number` | O | 장문 메시지 |
| mms | `number` | O | 이미지 + 장문 메시지 |
| ata | `number` | O | 알림톡 |
| cta | `number` | O | 친구톡 |

## Samples

### \(성공\) appName 수정

> **Sample Request**

```javascript
{
    "appName": "수정된 앱 이름"
}
```

> **Sample Response**

```javascript
{
    "redirectUri": "http://set.ms.coolsms.co.kr",
    "scope": [
        "message:read",
        "message:write"
    ],
    "thumbnail": {
        "name": "2BTZ6HLmal6x1Ao.png",
        "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
        "originalName": null
    },
    "profit": {
        "sms": 1,
        "lms": 1,
        "mms": 1,
        "ata": 1,
        "cta": 1
    },
    "appVersion": "1.0.1",
    "screenshots": [
        {
            "name": "57PKHgfBolSgvN7.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
        },
        {
            "name": "RaAB8w6tlC0hYow.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
        }
    ],
    "homepage": "http://developer.example.com",
    "categories": [
        "BUSINESS",
        "ENTER"
    ],
    "intro": "Test App",
    "description": "Description Of App",
    "stage": "DEVELOP",
    "status": "ACTIVE",
    "reasonBlocked": null,
    "email": "test@testemail.com",
    "log": [],
    "appName": "수정된 앱 이름",
    "accountId": "12925149",
    "clientId": "CIDNURIGOCOOLSMS",
    "appId": "b6dpHqh4K6Ax",
    "dateCreated": "2019-07-26T07:14:45.669Z",
    "dateUpdated": "2019-07-26T07:14:45.680Z"
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    appName: '수정된 앱 이름'
  },
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax'
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
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    appName: '수정된 앱 이름'
  },
  method: 'PUT',
  url: 'http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax";
$data = '{"appName":"수정된 앱 이름"}';

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"appName":"수정된 앱 이름"}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X PUT \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    -H 'Content-Type: application/json' \
    -d '{"appName":"수정된 앱 이름"}' \
    http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "appName": "수정된 앱 이름"
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
  uri := "http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax"
  data := strings.NewReader(`{"appName":"수정된 앱 이름"}`)

  req, err := http.NewRequest("PUT", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")
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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps/b6dpHqh4K6Ax";
    String parameters = "{\"appName\":\"수정된 앱 이름\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");
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

