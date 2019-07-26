# 템플릿 정보 수정

#### Request
```
PUT https://api.solapi.com/kakao/v1/templates/:templateId
```

템플릿의 정보를 수정합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` |  | O |

##### Path Parameters

| Name | Description |
| :--: | :---------: |
| :templateId | 템플릿 고유 아이디 |

##### Request Structure
```json
{
    "name": "string",
    "content": "string",
    "buttons": [
        {
            "buttonType": "string",
            "buttonName": "string",
            "linkMo": "string",
            "linkPc": "string",
            "linkAnd": "string",
            "linkIos": "string"
        }
    ]
}
```

##### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| name | `string` |  | 이름 |
| content | `string` |  | 템플릿 내용 |
| [buttons](#body-buttons) | `array` |  | 템플릿에 들어가는 버튼들 |


##### Body / buttons

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| buttonType | `string` | O | 설명 없음 |
| buttonName | `string` | O | 설명 없음 |
| linkMo | `string` |  | Mobile 주소 |
| linkPc | `string` |  | PC 주소 |
| linkAnd | `string` |  | Android 주소 |
| linkIos | `string` |  | IOS 주소 |


---

#### Samples

##### content 수정

> **Sample Request**

```json
{
    "content": "#{홍길동}님 회원가입을 환영 합니다."
}
```

> **Sample Response**

```json
{
    "status": "PENDING",
    "accountId": "12925149",
    "templateId": "KA01TP1907260745510305txrnAXDKjy",
    "name": "A0",
    "pfId": "PF01ID190726074551030kZ4ywTD3KIP",
    "content": "#{홍길동}님 회원가입을 환영 합니다.",
    "dateCreated": "2019-07-26T06:45:52.041Z",
    "dateUpdated": "2019-07-26T06:45:52.050Z",
    "buttons": [],
    "comments": []
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
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy'
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
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy";
$data = '{"content":"#{홍길동}님 회원가입을 환영 합니다."}';

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

url = "http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"content":"#{홍길동}님 회원가입을 환영 합니다."}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-H 'Content-Type: application/json' \
	-d '{"content":"#{홍길동}님 회원가입을 환영 합니다."}' \
	http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "content": "#{홍길동}님 회원가입을 환영 합니다."
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
  uri := "http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy"
  data := strings.NewReader(`{"content":"#{홍길동}님 회원가입을 환영 합니다."}`)

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/KA01TP1907260745510305txrnAXDKjy";
    String parameters = "{\"content\":\"#{홍길동}님 회원가입을 환영 합니다.\"}";

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

---
