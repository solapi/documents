# 플러스 친구를 추가

## Request

```text
POST https://api.solapi.com/kakao/v1/plus-friends
```

기존에 등록된 플러스 친구를 SOLAPI에 연동합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` |  | O |

### Request Structure

```javascript
{
    "searchId": "string",
    "phoneNumber": "string",
    "categoryCode": "string",
    "token": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| searchId | `string` | O | 플러스 친구 검색용 아이디 |
| phoneNumber | `string` | O | 핸드폰 번호 |
| categoryCode | `string` | O | 플러스 친구 카테고리 코드 |
| token | `string` | O | 연동 시 카카오톡으로 사용자에게 오는 토큰 |

## Samples

### 정상

> **Sample Request**

```javascript
{
    "searchId": "NURIGO",
    "phoneNumber": "01055555555",
    "categoryCode": "02536589547",
    "token": "123456789"
}
```

> **Sample Response**

```javascript
{
    "pfId": "KA01PF1907260745516663IBSWH6YiBw",
    "searchId": "NURIGO",
    "accountId": "19301859371938",
    "phoneNumber": "01055555555",
    "dateCreated": "2019-07-26T06:45:51.670Z",
    "dateUpdated": "2019-07-26T06:45:51.670Z"
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
    searchId: 'NURIGO',
    phoneNumber: '01055555555',
    categoryCode: '02536589547',
    token: '123456789'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/kakao/v1/plus-friends'
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
    searchId: 'NURIGO',
    phoneNumber: '01055555555',
    categoryCode: '02536589547',
    token: '123456789'
  },
  method: 'POST',
  url: 'http://api.solapi.com/kakao/v1/plus-friends'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/kakao/v1/plus-friends";
$data = '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}';

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n" . "Content-Type: application/json\r\n",
        'content' => $data,
        'method'  => 'POST'
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

url = "http://api.solapi.com/kakao/v1/plus-friends"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X POST \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    -H 'Content-Type: application/json' \
    -d '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}' \
    http://api.solapi.com/kakao/v1/plus-friends
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/plus-friends")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "searchId": "NURIGO",
  "phoneNumber": "01055555555",
  "categoryCode": "02536589547",
  "token": "123456789"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Post.new(uri.request_uri, headers)
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
  uri := "http://api.solapi.com/kakao/v1/plus-friends"
  data := strings.NewReader(`{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}`)

  req, err := http.NewRequest("POST", uri, data)
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
    String targetUrl = "http://api.solapi.com/kakao/v1/plus-friends";
    String parameters = "{\"searchId\":\"NURIGO\",\"phoneNumber\":\"01055555555\",\"categoryCode\":\"02536589547\",\"token\":\"123456789\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

