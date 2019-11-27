# 템플릿 정보 수정

## Request
```
PUT https://api.solapi.com/kakao/v1/templates/:templateId
```

템플릿의 정보를 수정합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` | `ACTIVE` | O |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :templateId | 템플릿 고유 아이디 |

### Request Structure
```json
{
    "name": "string",
    "content": "string",
    "buttons": "array"
}
```

### Body Params
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

## Samples

### setTemplate.spec.js

> **Sample Request**

```json
{
    "content": "#{홍길동}님 회원가입을 환영 합니다."
}
```

> **Sample Response**

```json
{
    "daou": {
        "accountId": "12925149",
        "templateId": "KA01TP191127221242003Vw6M9afZaXk",
        "name": "A0",
        "pfId": "PF01ID191127221242003AZvXyr6yy6y",
        "codes": [
            {
                "status": "PENDING",
                "comments": [],
                "code": "bizp_20190312165039251028888880",
                "service": "daou"
            },
            {
                "status": "PENDING",
                "comments": [],
                "code": "bizp_20190312165039251028888880",
                "service": "biz"
            }
        ],
        "content": "#{홍길동}님 회원가입을 환영 합니다.",
        "dateCreated": "2019-11-27T22:12:43.330Z",
        "dateUpdated": "2019-11-27T22:12:43.342Z",
        "buttons": []
    },
    "biz": {
        "accountId": "12925149",
        "templateId": "KA01TP191127221242003Vw6M9afZaXk",
        "name": "A0",
        "pfId": "PF01ID191127221242003AZvXyr6yy6y",
        "codes": [
            {
                "status": "PENDING",
                "comments": [],
                "code": "bizp_20190312165039251028888880",
                "service": "daou"
            },
            {
                "status": "PENDING",
                "comments": [],
                "code": "bizp_20190312165039251028888880",
                "service": "biz"
            }
        ],
        "content": "#{홍길동}님 회원가입을 환영 합니다.",
        "dateCreated": "2019-11-27T22:12:43.330Z",
        "dateUpdated": "2019-11-27T22:12:43.344Z",
        "buttons": []
    }
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
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk'
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk";
$data = '{"content":"#{홍길동}님 회원가입을 환영 합니다."}';

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

url = "http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
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
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"content":"#{홍길동}님 회원가입을 환영 합니다."}' \
	http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
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
  uri := "http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk"
  data := strings.NewReader(`{"content":"#{홍길동}님 회원가입을 환영 합니다."}`)

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/KA01TP191127221242003Vw6M9afZaXk";
    String parameters = "{\"content\":\"#{홍길동}님 회원가입을 환영 합니다.\"}";

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

---

> 문서 생성일 : 2019-11-27

