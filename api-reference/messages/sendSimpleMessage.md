# 단일 메시지

## Request
```
POST https://api.solapi.com/messages/v4/send
```

하나의 메시지를 발송합니다. 2개 이상의 메시지는 그룹 메시지를 사용하세요.

홈페이지의 [문자발송 내역](https://solapi.com/message-log/detail)에서 전송결과 내역을 확인하실 수 있습니다. (로그인 필요)

전송 내역(메시지 그룹, 메시지 목록)의 보관기간은 생성일 기준 6개월 입니다.
6개월이 지난 내역은 조회가 불가능합니다.


### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:write` | `role-message:write` | `ACTIVE` | `ACTIVE` |  |

### Request Structure
```json
{
    "message": "object",
    "strict": "boolean",
    "agent": "object"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| [message](#body-message) | `object` | O | 메시지에 대한 정보 |
| strict | `boolean` |  | 설명 없음 |
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
| imageId | `string` |  | Storage API에 등록된 이미지 아이디 [참고](https://docs.solapi.net/api-reference/storage) |
| [kakaoOptions](#body-message-kakaooptions) | `object` |  | 친구톡, 알림톡을 보내기 위한 옵션 |
| [customFields](#body-message-customfields) | `object` |  | 확장 필드로 사용. 키는 30자, 값은 100자 제한 |
| autoTypeDetect | `boolean` |  | 타입 설정이 없을 경우 자동으로 설정함. 기본 값은 true |

##### Body / message / kakaoOptions

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| pfId | `string` |  | 테스트에서 발급된 카카오톡 채널의 연동 아이디 |
| templateId | `string` |  | 알림톡 템플릿 아이디 |
| disableSms | `boolean` |  | 대체 발송 여부 |
| imageId | `string` |  | Storage API에 등록된 이미지 아이디 [참고](https://docs.solapi.net/api-reference/storage) |
| [buttons](#body-message-kakaooptions-buttons) | `array` |  | 알림톡 템플릿 버튼 목록 |


##### Body / message / kakaoOptions / buttons

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| buttonName | `string` | O | 버튼 이름 |
| buttonType | `string` | O | 버튼 종류(AL: 앱링크, WL: 웹링크, DS: 배송조회, BK: 키워드, MD: 전달 |
| linkMo | `string` |  | 모바일 링크(WL 웹링크) |
| linkPc | `string` |  | 웹 링크(WL 웹링크) |
| linkAnd | `string` |  | 안드로이드 링크(AL 앱링크) |
| linkIos | `string` |  | IOS 링크(AL 앱링크) |

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

## Response

### Response Structure
```json
{
    "groupId": "string",
    "messageId": "string",
    "accountId": "string",
    "statusMessage": "string",
    "statusCode": "string",
    "to": "string",
    "from": "string",
    "type": "string",
    "country": "string"
}
```

### Response Description
##### Response / 

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| groupId | `string` | O | 그룹 아이디 |
| messageId | `string` | O | 메시지 아이디 |
| accountId | `string` | O | 계정 고유 번호 |
| statusMessage | `string` | O | 상태 메시지 [참고](https://docs.solapi.net/api-reference/message-status-codes) |
| statusCode | `string` | O | 상태 코드 [참고](https://docs.solapi.net/api-reference/message-status-codes) |
| to | `string` | O | 수신번호 |
| from | `string` | O | 발신번호<br>사전 등록된 전화번호만 사용 가능 |
| type | `string` | O | 메시지 타입 |
| country | `string` | O | 국가번호 (현재 미지원) |


---

## Samples

### 메시지 발송 (type: Auto Detect)

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "내용"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920SIAOXNY53NII2QH",
    "to": "01000000001",
    "from": "029302266",
    "type": "SMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920L6CSANRNZEMSIAF",
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
      text: '내용'
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"내용"}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","text":"내용"}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"내용"}}' \
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
    "text": "내용"
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"내용"}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\"}}";

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

### 단문문자(SMS) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "내용",
        "type": "SMS"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920LGJS4O1BMNC89EX",
    "to": "01000000001",
    "from": "029302266",
    "type": "SMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920LSPBKFSVMNLMACR",
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
      text: '내용',
      type: 'SMS'
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}}' \
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
    "text": "내용",
    "type": "SMS"
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"SMS\"}}";

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

### 장문문자(LMS) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "subject": "별 헤는 밤",
        "text": "봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.",
        "type": "LMS"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920MASUMBLACJW6W20",
    "to": "01000000001",
    "from": "029302266",
    "type": "LMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920ZI9GL6QTMOB4L80",
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
      subject: '별 헤는 밤',
      text:
        '봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.',
      type: 'LMS'
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}}' \
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
    "subject": "별 헤는 밤",
    "text": "봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.",
    "type": "LMS"
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"subject\":\"별 헤는 밤\",\"text\":\"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.\",\"type\":\"LMS\"}}";

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

### 사진문자(MMS) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "subject": "제목",
        "text": "내용",
        "type": "MMS",
        "imageId": "FILEID191113003354156UvCuw3tubTl"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920FMCSHCVXGFUTCN9",
    "to": "01000000001",
    "from": "029302266",
    "type": "MMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920OVBXCIYYTKK6QG3",
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
      subject: '제목',
      text: '내용',
      type: 'MMS',
      imageId: 'FILEID191113003354156UvCuw3tubTl'
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}}' \
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
    "subject": "제목",
    "text": "내용",
    "type": "MMS",
    "imageId": "FILEID191113003354156UvCuw3tubTl"
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"subject\":\"제목\",\"text\":\"내용\",\"type\":\"MMS\",\"imageId\":\"FILEID191113003354156UvCuw3tubTl\"}}";

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

### 알림톡(ATA) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.",
        "type": "ATA",
        "kakaoOptions": {
            "pfId": "KA01PF190227072057634pRBhbpAw1w1",
            "templateId": "test_2019030716320324334488000",
            "buttons": [
                {
                    "buttonType": "WL",
                    "buttonName": "1:1문의",
                    "linkMo": "https://www.example.com"
                }
            ]
        }
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920UDCBEDQKZRCFIS6",
    "to": "01000000001",
    "from": "029302266",
    "type": "ATA",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920WWJOPCVKBPZINPA",
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
      text:
        "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.",
      type: 'ATA',
      kakaoOptions: {
        pfId: 'KA01PF190227072057634pRBhbpAw1w1',
        templateId: 'test_2019030716320324334488000',
        buttons: [
          {
            buttonType: 'WL',
            buttonName: '1:1문의',
            linkMo: 'https://www.example.com'
          }
        ]
      }
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}}' \
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
    "text": "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.",
    "type": "ATA",
    "kakaoOptions": {
      "pfId": "KA01PF190227072057634pRBhbpAw1w1",
      "templateId": "test_2019030716320324334488000",
      "buttons": [
        {
          "buttonType": "WL",
          "buttonName": "1:1문의",
          "linkMo": "https://www.example.com"
        }
      ]
    }
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.\",\"type\":\"ATA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\",\"templateId\":\"test_2019030716320324334488000\",\"buttons\":[{\"buttonType\":\"WL\",\"buttonName\":\"1:1문의\",\"linkMo\":\"https://www.example.com\"}]}}}";

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

### 친구톡(CTA) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "내용",
        "type": "CTA",
        "kakaoOptions": {
            "pfId": "KA01PF190227072057634pRBhbpAw1w1"
        }
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920IWAP3LQEV4EFBBN",
    "to": "01000000001",
    "from": "029302266",
    "type": "CTA",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920DDB5KY23GWA5XMI",
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
      text: '내용',
      type: 'CTA',
      kakaoOptions: {
        pfId: 'KA01PF190227072057634pRBhbpAw1w1'
      }
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}}' \
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
    "text": "내용",
    "type": "CTA",
    "kakaoOptions": {
      "pfId": "KA01PF190227072057634pRBhbpAw1w1"
    }
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"CTA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\"}}}";

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

### 친구톡 사진(CTI) 발송

> **Sample Request**

```json
{
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "내용",
        "type": "CTI",
        "kakaoOptions": {
            "pfId": "KA01PF190227072057634pRBhbpAw1w1",
            "imageId": "FILEID191113003354156UvCuw3tubTl"
        }
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V202009091409208KA9RNKNWNBWWRR",
    "to": "01000000001",
    "from": "029302266",
    "type": "CTI",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920P85SVEZSHFP90Z1",
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
      text: '내용',
      type: 'CTI',
      kakaoOptions: {
        pfId: 'KA01PF190227072057634pRBhbpAw1w1',
        imageId: 'FILEID191113003354156UvCuw3tubTl'
      }
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}}';

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
data = '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}}'

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
	-d '{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}}' \
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
    "text": "내용",
    "type": "CTI",
    "kakaoOptions": {
      "pfId": "KA01PF190227072057634pRBhbpAw1w1",
      "imageId": "FILEID191113003354156UvCuw3tubTl"
    }
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
  data := strings.NewReader(`{"message":{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}}`)

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
    String parameters = "{\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"CTI\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\",\"imageId\":\"FILEID191113003354156UvCuw3tubTl\"}}}";

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

### sendSimpleMessage

> **Sample Request**

```json
{
    "strict": false,
    "message": {
        "to": "01000000001",
        "from": "029302266",
        "text": "뷁뒑뤩궭훩홊",
        "type": "SMS"
    }
}
```

> **Sample Response**

```json
{
    "groupId": "G4V20200909140920NGELDMOQFVLZU1M",
    "to": "01000000001",
    "from": "029302266",
    "type": "SMS",
    "statusMessage": "정상 접수(이통사로 접수 예정) ",
    "country": "82",
    "messageId": "M4V20200909140920YSAQMMBU6GDYEWB",
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
    strict: false,
    message: {
      to: '01000000001',
      from: '029302266',
      text: '뷁뒑뤩궭훩홊',
      type: 'SMS'
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/send";
$data = '{"strict":false,"message":{"to":"01000000001","from":"029302266","text":"뷁뒑뤩궭훩홊","type":"SMS"}}';

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
data = '{"strict":false,"message":{"to":"01000000001","from":"029302266","text":"뷁뒑뤩궭훩홊","type":"SMS"}}'

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
	-d '{"strict":false,"message":{"to":"01000000001","from":"029302266","text":"뷁뒑뤩궭훩홊","type":"SMS"}}' \
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
  "strict": false,
  "message": {
    "to": "01000000001",
    "from": "029302266",
    "text": "뷁뒑뤩궭훩홊",
    "type": "SMS"
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
  data := strings.NewReader(`{"strict":false,"message":{"to":"01000000001","from":"029302266","text":"뷁뒑뤩궭훩홊","type":"SMS"}}`)

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
    String parameters = "{\"strict\":false,\"message\":{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"뷁뒑뤩궭훩홊\",\"type\":\"SMS\"}}";

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

> 문서 생성일 : 2020-09-09

