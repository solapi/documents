# 여러건 발송

## Request
```
POST https://api.solapi.com/messages/v4/send-many
```

하나 이상의 메시지를 발송합니다. 대량 발송은 그룹 메시지를 사용하세요.

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
    "messages": "Array",
    "strict": "boolean",
    "agent": "object"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| messages | `Array` | O | 발송할 메시지 내용 |
| strict | `boolean` |  | 설명 없음 |
| [agent](#body-agent) | `object` |  | 에이전트 |

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
| statusMessage | `string` | O | 상태 메시지 [참고](docs.solapi.com/api-reference/message-status-codes) |
| statusCode | `string` | O | 상태 코드 [참고](docs.solapi.com/api-reference/message-status-codes) |
| to | `string` | O | 수신번호 |
| from | `string` | O | 발신번호<br>사전 등록된 전화번호만 사용 가능 |
| type | `string` | O | 메시지 타입 |
| country | `string` | O | 국가번호 (기본: 82, 미국(캐나다):1, 중국: 86, 일본: 81) |


---

## Samples

### 메시지 발송 (type: Auto Detect)

> **Sample Request**

```json
{
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "내용"
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {
            "82": 1
        },
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.392Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.413Z",
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.431Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.431Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825UTMBWD3F7YRY3N1",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825UTMBWD3F7YRY3N1",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.394Z",
    "dateUpdated": "2021-07-14T06:58:25.431Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: '내용'
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용"}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용"}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"내용"}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "내용"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"내용"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\"}]}";

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
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "내용",
            "type": "SMS"
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {
            "82": 1
        },
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.487Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.509Z",
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.528Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.528Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825FB7HVKTCCVBPHBL",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825FB7HVKTCCVBPHBL",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.490Z",
    "dateUpdated": "2021-07-14T06:58:25.528Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: '내용',
        type: 'SMS'
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "내용",
      "type": "SMS"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"SMS"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"SMS\"}]}";

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
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "subject": "별 헤는 밤",
            "text": "봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.",
            "type": "LMS"
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {},
        "lms": {
            "82": 1
        },
        "mms": {},
        "ata": {},
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.588Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.610Z",
            "message": "국가코드(82)의 장문문자(LMS) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.628Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.628Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825AJASCTZ8AQOW9VV",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825AJASCTZ8AQOW9VV",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.591Z",
    "dateUpdated": "2021-07-14T06:58:25.628Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        subject: '별 헤는 밤',
        text:
          '봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.',
        type: 'LMS'
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "subject": "별 헤는 밤",
      "text": "봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.",
      "type": "LMS"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","subject":"별 헤는 밤","text":"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.","type":"LMS"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"subject\":\"별 헤는 밤\",\"text\":\"봄이 어머니, 패, 한 부끄러운 이웃 별 옥 계집애들의 계십니다. 내린 아무 아름다운 나는 이름을 있습니다. 위에도 하나에 못 북간도에 새워 강아지, 말 비둘기, 헤는 듯합니다. 가을로 했던 위에도 이름자를 봅니다. 아무 새겨지는 별 너무나 토끼, 듯합니다. 청춘이 헤는 토끼, 계절이 많은 듯합니다. 아름다운 못 내 그리고 아직 청춘이 라이너 버리었습니다. 벌레는 까닭이요, 어머니 봅니다. 속의 아이들의 나는 프랑시스 있습니다. 밤이 강아지, 하나 계십니다. 잔디가 이름과 별 프랑시스 하나에 하나 계십니다.\",\"type\":\"LMS\"}]}";

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
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "subject": "제목",
            "text": "내용",
            "type": "MMS",
            "imageId": "FILEID191113003354156UvCuw3tubTl"
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {},
        "lms": {},
        "mms": {
            "82": 1
        },
        "ata": {},
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.688Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.715Z",
            "message": "국가코드(82)의 포토문자(MMS) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.732Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.732Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825B6PKBGMLU2Z3CAF",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825B6PKBGMLU2Z3CAF",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.690Z",
    "dateUpdated": "2021-07-14T06:58:25.732Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        subject: '제목',
        text: '내용',
        type: 'MMS',
        imageId: 'FILEID191113003354156UvCuw3tubTl'
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "subject": "제목",
      "text": "내용",
      "type": "MMS",
      "imageId": "FILEID191113003354156UvCuw3tubTl"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","subject":"제목","text":"내용","type":"MMS","imageId":"FILEID191113003354156UvCuw3tubTl"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"subject\":\"제목\",\"text\":\"내용\",\"type\":\"MMS\",\"imageId\":\"FILEID191113003354156UvCuw3tubTl\"}]}";

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
    "messages": [
        {
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
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {},
        "lms": {},
        "mms": {},
        "ata": {
            "82": 1
        },
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.793Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.820Z",
            "message": "국가코드(82)의 알림톡(ATA) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.838Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.838Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V202107141558259BJMUDOQ0CLDV0P",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V202107141558259BJMUDOQ0CLDV0P",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.795Z",
    "dateUpdated": "2021-07-14T06:58:25.838Z"
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
    messages: [
      {
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
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
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
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488000","buttons":[{"buttonType":"WL","buttonName":"1:1문의","linkMo":"https://www.example.com"}]}}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다. #{입금정보} 관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다. 감사합니다.\",\"type\":\"ATA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\",\"templateId\":\"test_2019030716320324334488000\",\"buttons\":[{\"buttonType\":\"WL\",\"buttonName\":\"1:1문의\",\"linkMo\":\"https://www.example.com\"}]}}]}";

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
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "내용",
            "type": "CTA",
            "kakaoOptions": {
                "pfId": "KA01PF190227072057634pRBhbpAw1w1"
            }
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {},
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {
            "82": 1
        },
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.899Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.924Z",
            "message": "국가코드(82)의 친구톡(CTA) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.941Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.941Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825OSOSZP37ZBTK5DT",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825OSOSZP37ZBTK5DT",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.902Z",
    "dateUpdated": "2021-07-14T06:58:25.941Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: '내용',
        type: 'CTA',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1'
        }
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "내용",
      "type": "CTA",
      "kakaoOptions": {
        "pfId": "KA01PF190227072057634pRBhbpAw1w1"
      }
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"CTA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\"}}]}";

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
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "내용",
            "type": "CTI",
            "kakaoOptions": {
                "pfId": "KA01PF190227072057634pRBhbpAw1w1",
                "imageId": "FILEID191113003354156UvCuw3tubTl"
            }
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 1,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {},
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {},
        "cti": {
            "82": 1
        },
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:26.000Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:26.026Z",
            "message": "국가코드(82)의 친구톡 이미지(CTI) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:26.043Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:26.043Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155826M5NOYYG6VGWKK3E",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155826M5NOYYG6VGWKK3E",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:26.002Z",
    "dateUpdated": "2021-07-14T06:58:26.044Z"
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: '내용',
        type: 'CTI',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1',
          imageId: 'FILEID191113003354156UvCuw3tubTl'
        }
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "내용",
      "type": "CTI",
      "kakaoOptions": {
        "pfId": "KA01PF190227072057634pRBhbpAw1w1",
        "imageId": "FILEID191113003354156UvCuw3tubTl"
      }
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"내용","type":"CTI","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","imageId":"FILEID191113003354156UvCuw3tubTl"}}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"내용\",\"type\":\"CTI\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\",\"imageId\":\"FILEID191113003354156UvCuw3tubTl\"}}]}";

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

### sendMany

> **Sample Request**

```json
{
    "messages": [
        {
            "to": [
                "01000000001",
                "01000000001"
            ],
            "from": "029302266",
            "text": "내용",
            "autoTypeDetect": true
        }
    ]
}
```

> **Sample Response**

```json
{
    "count": {
        "total": 2,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 1,
        "registeredSuccess": 1
    },
    "countForCharge": {
        "sms": {
            "82": 1
        },
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {},
        "cti": {},
        "nsa": {},
        "rcs_sms": {},
        "rcs_lms": {},
        "rcs_mms": {},
        "rcs_tpl": {}
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 50,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "app": {
        "profit": {
            "sms": 0,
            "lms": 0,
            "mms": 0,
            "ata": 0,
            "cta": 0,
            "cti": 0,
            "nsa": 0,
            "rcs_sms": 0,
            "rcs_lms": 0,
            "rcs_mms": 0,
            "rcs_tpl": 0
        },
        "appId": null,
        "version": null
    },
    "serviceMethod": "MT",
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "createAt": "2021-07-14T06:58:25.120Z",
            "message": "[::ffff:127.0.0.1] 메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.142Z",
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다."
        },
        {
            "createAt": "2021-07-14T06:58:25.159Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 0
        }
    ],
    "status": "SENDING",
    "dateSent": "2021-07-14T06:58:25.159Z",
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": false,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20210714155825HFKJIBGN02UP9ZY",
    "accountId": "12925149",
    "apiVersion": "4",
    "customFields": {},
    "hint": null,
    "groupId": "G4V20210714155825HFKJIBGN02UP9ZY",
    "price": {
        "82": []
    },
    "dateCreated": "2021-07-14T06:58:25.123Z",
    "dateUpdated": "2021-07-14T06:58:25.159Z"
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
    messages: [
      {
        to: ['01000000001', '01000000001'],
        from: '029302266',
        text: '내용',
        autoTypeDetect: true
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/send-many'
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
$url = "http://api.solapi.com/messages/v4/send-many";
$data = '{"messages":[{"to":["01000000001","01000000001"],"from":"029302266","text":"내용","autoTypeDetect":true}]}';

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

url = "http://api.solapi.com/messages/v4/send-many"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":["01000000001","01000000001"],"from":"029302266","text":"내용","autoTypeDetect":true}]}'

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
	-d '{"messages":[{"to":["01000000001","01000000001"],"from":"029302266","text":"내용","autoTypeDetect":true}]}' \
	http://api.solapi.com/messages/v4/send-many
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/send-many")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": [
        "01000000001",
        "01000000001"
      ],
      "from": "029302266",
      "text": "내용",
      "autoTypeDetect": true
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/send-many"
  data := strings.NewReader(`{"messages":[{"to":["01000000001","01000000001"],"from":"029302266","text":"내용","autoTypeDetect":true}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/send-many";
    String parameters = "{\"messages\":[{\"to\":[\"01000000001\",\"01000000001\"],\"from\":\"029302266\",\"text\":\"내용\",\"autoTypeDetect\":true}]}";

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

> 문서 생성일 : 2021-07-14

