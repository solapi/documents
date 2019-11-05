# 템플릿 추가

## Request
```
POST https://api.solapi.com/kakao/v1/templates/:service
```

템플릿을 새롭게 등록하거나 기존에 등록된 템플릿에 연동처를 추가합니다. 새로운 템플릿은 content가 필드가 필수 입력 값이며 연동처만 추가할 경우 content, buttons 필드를 입력할 수 없습니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` | `ACTIVE` | O |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :service | 카카오톡채널 연동처 |

### Request Structure
```json
{
    "pfId": "string",
    "name": "string",
    "content": "string",
    "buttons": "array"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| pfId | `string` | O | 카카오톡채널 고유 아이디 |
| name | `string` | O | 이름 |
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

### 템플릿 등록

> **Sample Request**

```json
{
    "pfId": "PF01ID191105201456599GiZM5ByaZqx",
    "name": "회원가입",
    "content": "#{홍길동}님 회원가입을 환영 합니다."
}
```

> **Sample Response**

```json
{
    "name": "회원가입",
    "pfId": "PF01ID191105201456599GiZM5ByaZqx",
    "accountId": "12925149",
    "buttons": [],
    "codes": [
        {
            "status": "PENDING",
            "comments": [],
            "service": "daou"
        }
    ],
    "content": "#{홍길동}님 회원가입을 환영 합니다.",
    "dateCreated": "2019-11-05T20:14:57.441Z",
    "dateUpdated": "2019-11-05T20:14:57.441Z",
    "templateId": "KA01TP191105201457442ZI96va1rh3j"
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
    pfId: 'PF01ID191105201456599GiZM5B...',
    name: '회원가입',
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/kakao/v1/templates/daou'
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
    pfId: 'PF01ID191105201456599GiZM5B...',
    name: '회원가입',
    content: '#{홍길동}님 회원가입을 환영 합니다.'
  },
  method: 'POST',
  url: 'http://api.solapi.com/kakao/v1/templates/daou'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/kakao/v1/templates/daou";
$data = '{"pfId":"PF01ID191105201456599GiZM5B...","name":"회원가입","content":"#{홍길동}님 회원가입을 환영 합니다."}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/kakao/v1/templates/daou"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"pfId":"PF01ID191105201456599GiZM5B...","name":"회원가입","content":"#{홍길동}님 회원가입을 환영 합니다."}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"pfId":"PF01ID191105201456599GiZM5B...","name":"회원가입","content":"#{홍길동}님 회원가입을 환영 합니다."}' \
	http://api.solapi.com/kakao/v1/templates/daou
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/daou")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "pfId": "PF01ID191105201456599GiZM5B...",
  "name": "회원가입",
  "content": "#{홍길동}님 회원가입을 환영 합니다."
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
  uri := "http://api.solapi.com/kakao/v1/templates/daou"
  data := strings.NewReader(`{"pfId":"PF01ID191105201456599GiZM5B...","name":"회원가입","content":"#{홍길동}님 회원가입을 환영 합니다."}`)

  req, err := http.NewRequest("POST", uri, data)
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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/daou";
    String parameters = "{\"pfId\":\"PF01ID191105201456599GiZM5B...\",\"name\":\"회원가입\",\"content\":\"#{홍길동}님 회원가입을 환영 합니다.\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

> 문서 생성일 : 2019-11-05

