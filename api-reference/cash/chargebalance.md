# 사용자 충전

> 문서 생성일 : 2019-08-06

## 사용자 충전

### Request

```text
POST https://api.solapi.com/cash/v1/balance
```

사용자가 결제를 해 충전을 합니다.

#### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `cash:write` | `role-cash:write` | `ACTIVE` |  | O |

#### 2차 인증 필요

| ARS 전화 인증 | 이메일 OTP |
| :---: | :---: |
|  | O |

#### Request Structure

```javascript
{
    "amount": "number",
    "paymentId": "string"
}
```

#### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| amount | `number` | O | 합계 금액 |
| paymentId | `string` | O | 결제 ID |

### Samples

#### 정상

> **Sample Request**

```javascript
{
    "amount": 10000,
    "paymentId": "1407974467827303801565071718686"
}
```

> **Sample Response**

```javascript
{
    "accountId": "19041920726336",
    "oldBalance": 10130,
    "newBalance": 20130,
    "oldPoint": 0,
    "newPoint": 0,
    "balanceAmount": 10000,
    "pointAmount": 0,
    "type": "RECHARGE",
    "historyId": "5d491966384bbe6e51a2ceb6"
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
    amount: 10000,
    paymentId: '140797446782730380156507171...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/cash/v1/balance'
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
    amount: 10000,
    paymentId: '140797446782730380156507171...'
  },
  method: 'POST',
  url: 'http://api.solapi.com/cash/v1/balance'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/cash/v1/balance";
$data = '{"amount":10000,"paymentId":"140797446782730380156507171..."}';

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

url = "http://api.solapi.com/cash/v1/balance"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"amount":10000,"paymentId":"140797446782730380156507171..."}'

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
    -d '{"amount":10000,"paymentId":"140797446782730380156507171..."}' \
    http://api.solapi.com/cash/v1/balance
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/balance")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "amount": 10000,
  "paymentId": "140797446782730380156507171..."
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
  uri := "http://api.solapi.com/cash/v1/balance"
  data := strings.NewReader(`{"amount":10000,"paymentId":"140797446782730380156507171..."}`)

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
    String targetUrl = "http://api.solapi.com/cash/v1/balance";
    String parameters = "{\"amount\":10000,\"paymentId\":\"140797446782730380156507171...\"}";

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

