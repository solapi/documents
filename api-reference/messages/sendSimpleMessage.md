# 단일 메시지

## Request
```
POST https://api.solapi.com/messages/v4/send
```

하나의 메시지를 발송합니다. 2개 이상의 메시지는 그룹 메시지를 사용하세요.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:write` | `role-message:write` | `ACTIVE` | `ACTIVE` | O |

### Request Structure
```json
{
    "message": "object",
    "agent": "object"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| [message](#body-message) | `object` | O | 메시지에 대한 정보 |
| [agent](#body-agent) | `object` |  | 에이전트 |

##### Body / message

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| to | `string` | O | 수신번호 |
| from | `string` | O | 발신번호<br>사전 등록된 전화번호만 사용 가능 |
| text | `string` | O | 메시지 내용<br>한글 1,000자, 영문 2,000자 제한 |
| type | `string` |  | 메시지 타입 |
| country | `string` |  | 국가번호 (현재 미지원) |
| subject | `string` |  | 메시지 제목<br>한글 20자, 영문 40자 제한 |
| imageId | `string` |  | 이미지 아이디 |
| [kakaoOptions](#body-message-kakaooptions) | `object` |  | 설명 없음 |
| [customFields](#body-message-customfields) | `object` |  | 확장 필드로 사용. 키는 30자, 값은 100자 제한 |
| autoTypeDetect | `boolean` |  | 타입 설정이 없을 경우 자동으로 설정함. 기본 값은 true |

##### Body / message / kakaoOptions

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| pfId | `string` |  | SOLAPI와 연동된 플러스 친구 고유 아이디 |
| templateId | `string` |  | 알림톡 템플릿 아이디 |
| disableSms | `boolean` |  | 대체 발송 여부 |
| [buttons](#body-message-kakaooptions-buttons) | `array` |  | 알림톡 템플릿 버튼 목록 |


##### Body / message / kakaoOptions / buttons

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| buttonName | `string` | O | 버튼 이름 |
| buttonType | `string` | O | 버튼 종류 |
| linkMo | `string` |  | 모바일 링크 |
| linkPc | `string` |  | 웹 링크 |
| linkAnd | `string` |  | 안드로이드 링크 |
| linkIos | `string` |  | IOS 링크 |

##### Body / message / customFields

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |

##### Body / agent

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| appId | `string` |  | 앱 아이디 |
| osPlatform | `string` |  | OS 플렛폼 |
| sdkVersion | `string` |  | SDK 버전 |


---

## Samples

### sendSimpleMessage

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "test message"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20190919083538APJLKSASCDC3LFR",
    "to": "01000000001",
    "from": "029302266",
    "type": "SMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V201909190835381XELFGPINDEKIYL",
    "statusCode": "2000",
    "accountId": "12925149"
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
    message: {
      to: '01000000001',
      from: '029302266',
      text: 'test message'
    }
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send'
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
    message: {
      to: '01000000001',
      from: '029302266',
      text: 'test message'
    }
  },
  method: 'POST',
  url: 'http://api.solapi.com/messages/v4/send'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"test message"}}';

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

url = "http://api.solapi.com/messages/v4/send"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"message":{"to":"01000000001","from":"029302266","text":"test message"}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"test message"}}' \
	http://api.solapi.com/messages/v4/send
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "message": {
    "to": "01000000001",
    "from": "029302266",
    "text": "test message"
  }
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
  uri := "http://api.solapi.com/messages/v4/send"
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"test message"}}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send";
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"test message\"}}";

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

> 문서 생성일 : 2019-09-18

