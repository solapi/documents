# 잔액이전

#### Request
```
POST https://api.solapi.com/cash/v1/transfer
```

잔액을 다른 계정에 이전합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `cash:write` | `role-cash:write` | `ACTIVE` |  | O |

##### 2차 인증 필요

| ARS 전화 인증 | 이메일 OTP |
| :---------: | :------: |
|  | O |

##### Request Structure
```json
{
    "targetAccountId": "string",
    "amount": "number",
    "accountId": "string"
}
```

##### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| targetAccountId | `string` | O | 잔액 이전을 받을 계정 ID |
| amount | `number` | O | 합계 금액 |
| accountId | `string` |  | 계정 고유 아이디 |


---

#### Samples

##### 캐쉬 이전

> **Sample Request**

```json
{
    "amount": 1000,
    "targetAccountId": "214727"
}
```

> **Sample Response**

```json
"Success"
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
    amount: 1000,
    targetAccountId: '214727'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/cash/v1/transfer'
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
    amount: 1000,
    targetAccountId: '214727'
  },
  method: 'POST',
  url: 'http://api.solapi.com/cash/v1/transfer'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/cash/v1/transfer";
$data = '{"amount":1000,"targetAccountId":"214727"}';

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

url = "http://api.solapi.com/cash/v1/transfer"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"amount":1000,"targetAccountId":"214727"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-H 'Content-Type: application/json' \
	-d '{"amount":1000,"targetAccountId":"214727"}' \
	http://api.solapi.com/cash/v1/transfer
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/transfer")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "amount": 1000,
  "targetAccountId": "214727"
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
  uri := "http://api.solapi.com/cash/v1/transfer"
  data := strings.NewReader(`{"amount":1000,"targetAccountId":"214727"}`)

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
    String targetUrl = "http://api.solapi.com/cash/v1/transfer";
    String parameters = "{\"amount\":1000,\"targetAccountId\":\"214727\"}";

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

---
