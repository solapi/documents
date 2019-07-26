# 그룹 메시지 추가

#### Request
```
PUT https://api.solapi.com/messages/v4/groups/:groupId/messages
```

그룹에 메시지를 추가합니다. 접수 실패건은 저장되지만 발송은 되지 않습니다.<br>그룹메시지 추가 API에 다음 3가지 제한사항이 있습니다.<br>- 하나의 요청의 총 데이터 크기는 15MB를 넘을 수 없습니다.<br>- 하나의 요청에 수신번호는 10,000 개를 넘을 수 없습니다.<br>- 하나의 그룹에 담을 수 있는 메시지는 1,000,000 개 제한입니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:write` | `role-message:write` | `ACTIVE` | `ACTIVE` | O |

##### Path Parameters

| Name | Description |
| :--: | :---------: |
| :groupId | 설명 없음 |

##### Request Structure
```json
{
    "messages": [
        {
            "to": "string",
            "from": "string",
            "text": "string",
            "type": "string",
            "country": "string",
            "subject": "string",
            "imageId": "string",
            "kakaoOptions": {
                "pfId": "string",
                "templateId": "string",
                "disableSms": "boolean",
                "buttons": [
                    {
                        "buttonName": "string",
                        "buttonType": "string",
                        "linkMo": "string",
                        "linkPc": "string",
                        "linkAnd": "string",
                        "linkIos": "string"
                    }
                ]
            },
            "customFields": {},
            "autoTypeDetect": "boolean"
        }
    ]
}
```

##### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| [messages](#body-messages) | `Array` |  | 발송할 메시지 내용 |


##### Body / messages

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| to | `string` | O | 수신번호 |
| from | `string` | O | 발신번호 |
| text | `string` | O | 메시지 내용 |
| type | `string` |  | 메시지 타입 |
| country | `string` |  | 국가번호 |
| subject | `string` |  | 메시지 제목 |
| imageId | `string` |  | 이미지 아이디 |
| [kakaoOptions](#body-messages-kakaooptions) | `object` |  | 설명 없음 |
| [customFields](#body-messages-customfields) | `object` |  | 확장 필드로 사용. 키는 30자, 값은 100자 제한 |
| autoTypeDetect | `boolean` |  | 타입 설정이 없을 경우 자동으로 설정함. 기본 값은 true |

##### Body / messages / kakaoOptions

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| pfId | `string` |  | SOLAPI와 연동된 플러스 친구 고유 아이디 |
| templateId | `string` |  | 알림톡 템플릿 아이디 |
| disableSms | `boolean` |  | 대체 발송 여부 |
| [buttons](#body-messages-kakaooptions-buttons) | `array` |  | 알림톡 템플릿 버튼 목록 |


##### Body / messages / kakaoOptions / buttons

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| buttonName | `string` | O | 버튼 이름 |
| buttonType | `string` | O | 버튼 종류 |
| linkMo | `string` |  | 모바일 링크 |
| linkPc | `string` |  | 웹 링크 |
| linkAnd | `string` |  | 안드로이드 링크 |
| linkIos | `string` |  | IOS 링크 |

##### Body / messages / customFields

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |


---

#### Samples

##### 단문문자(SMS) 추가

> **Sample Request**

```json
{
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "test message",
            "type": "SMS"
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301J95ZLEXCUSSRGQJ",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: 'test message',
        type: 'SMS'
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: 'test message',
        type: 'SMS'
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","type":"SMS"}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","type":"SMS"}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","type":"SMS"}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "test message",
      "type": "SMS"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"test message","type":"SMS"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"test message\",\"type\":\"SMS\"}]}";

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

##### 장문문자(LMS) 추가

> **Sample Request**

```json
{
    "messages": [
        {
            "subject": "testSubject",
            "to": "01000000001",
            "from": "029302266",
            "text": "lms test message",
            "type": "LMS"
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "LMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301RYBJJLT0JK2IUEB",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        subject: 'testSubject',
        to: '01000000001',
        from: '029302266',
        text: 'lms test message',
        type: 'LMS'
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
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
    messages: [
      {
        subject: 'testSubject',
        to: '01000000001',
        from: '029302266',
        text: 'lms test message',
        type: 'LMS'
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
$data = '{"messages":[{"subject":"testSubject","to":"01000000001","from":"029302266","text":"lms test message","type":"LMS"}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"subject":"testSubject","to":"01000000001","from":"029302266","text":"lms test message","type":"LMS"}]}'

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
	-d '{"messages":[{"subject":"testSubject","to":"01000000001","from":"029302266","text":"lms test message","type":"LMS"}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "subject": "testSubject",
      "to": "01000000001",
      "from": "029302266",
      "text": "lms test message",
      "type": "LMS"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"subject":"testSubject","to":"01000000001","from":"029302266","text":"lms test message","type":"LMS"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"subject\":\"testSubject\",\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"lms test message\",\"type\":\"LMS\"}]}";

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

##### 포토문자(MMS) 추가

> **Sample Request**

```json
{
    "messages": [
        {
            "subject": "testSubject",
            "to": "01000000002",
            "from": "029302266",
            "text": "mms test message",
            "type": "MMS",
            "imageId": "TESTIMAGEID"
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000002",
            "from": "029302266",
            "type": "MMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301GRPMGEHGV0HDC9A",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        subject: 'testSubject',
        to: '01000000002',
        from: '029302266',
        text: 'mms test message',
        type: 'MMS',
        imageId: 'TESTIMAGEID'
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
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
    messages: [
      {
        subject: 'testSubject',
        to: '01000000002',
        from: '029302266',
        text: 'mms test message',
        type: 'MMS',
        imageId: 'TESTIMAGEID'
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
$data = '{"messages":[{"subject":"testSubject","to":"01000000002","from":"029302266","text":"mms test message","type":"MMS","imageId":"TESTIMAGEID"}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"subject":"testSubject","to":"01000000002","from":"029302266","text":"mms test message","type":"MMS","imageId":"TESTIMAGEID"}]}'

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
	-d '{"messages":[{"subject":"testSubject","to":"01000000002","from":"029302266","text":"mms test message","type":"MMS","imageId":"TESTIMAGEID"}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "subject": "testSubject",
      "to": "01000000002",
      "from": "029302266",
      "text": "mms test message",
      "type": "MMS",
      "imageId": "TESTIMAGEID"
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"subject":"testSubject","to":"01000000002","from":"029302266","text":"mms test message","type":"MMS","imageId":"TESTIMAGEID"}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"subject\":\"testSubject\",\"to\":\"01000000002\",\"from\":\"029302266\",\"text\":\"mms test message\",\"type\":\"MMS\",\"imageId\":\"TESTIMAGEID\"}]}";

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

##### 정상

> **Sample Request**

```json
{
    "messages": [
        {
            "to": "01000000003",
            "from": "029302266",
            "text": "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.",
            "type": "ATA",
            "kakaoOptions": {
                "pfId": "KA01PF190227072057634pRBhbpAw1w1",
                "templateId": "test_2019030716320324334488006",
                "buttons": [
                    {
                        "buttonName": "앱 링크",
                        "buttonType": "AL",
                        "linkIos": "https://#{url}",
                        "linkAnd": "http://#{url}"
                    },
                    {
                        "buttonName": "웹 링크",
                        "buttonType": "WL",
                        "linkMo": "https://www.coolsms.co.kr"
                    },
                    {
                        "buttonName": "배송조회",
                        "buttonType": "DS"
                    },
                    {
                        "buttonName": "키워드",
                        "buttonType": "BK"
                    },
                    {
                        "buttonName": "전달",
                        "buttonType": "MD"
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
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000003",
            "from": "029302266",
            "type": "ATA",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301EAHLDNR5SYOEZU4",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        to: '01000000003',
        from: '029302266',
        text:
          "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.",
        type: 'ATA',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1',
          templateId: 'test_2019030716320324334488006',
          buttons: [
            {
              buttonName: '앱 링크',
              buttonType: 'AL',
              linkIos: 'https://#{url}',
              linkAnd: 'http://#{url}'
            },
            {
              buttonName: '웹 링크',
              buttonType: 'WL',
              linkMo: 'https://www.coolsms.co.kr'
            },
            {
              buttonName: '배송조회',
              buttonType: 'DS'
            },
            {
              buttonName: '키워드',
              buttonType: 'BK'
            },
            {
              buttonName: '전달',
              buttonType: 'MD'
            }
          ]
        }
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
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
    messages: [
      {
        to: '01000000003',
        from: '029302266',
        text:
          "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.",
        type: 'ATA',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1',
          templateId: 'test_2019030716320324334488006',
          buttons: [
            {
              buttonName: '앱 링크',
              buttonType: 'AL',
              linkIos: 'https://#{url}',
              linkAnd: 'http://#{url}'
            },
            {
              buttonName: '웹 링크',
              buttonType: 'WL',
              linkMo: 'https://www.coolsms.co.kr'
            },
            {
              buttonName: '배송조회',
              buttonType: 'DS'
            },
            {
              buttonName: '키워드',
              buttonType: 'BK'
            },
            {
              buttonName: '전달',
              buttonType: 'MD'
            }
          ]
        }
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
$data = '{"messages":[{"to":"01000000003","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488006","buttons":[{"buttonName":"앱 링크","buttonType":"AL","linkIos":"https://#{url}","linkAnd":"http://#{url}"},{"buttonName":"웹 링크","buttonType":"WL","linkMo":"https://www.coolsms.co.kr"},{"buttonName":"배송조회","buttonType":"DS"},{"buttonName":"키워드","buttonType":"BK"},{"buttonName":"전달","buttonType":"MD"}]}}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000003","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488006","buttons":[{"buttonName":"앱 링크","buttonType":"AL","linkIos":"https://#{url}","linkAnd":"http://#{url}"},{"buttonName":"웹 링크","buttonType":"WL","linkMo":"https://www.coolsms.co.kr"},{"buttonName":"배송조회","buttonType":"DS"},{"buttonName":"키워드","buttonType":"BK"},{"buttonName":"전달","buttonType":"MD"}]}}]}'

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
	-d '{"messages":[{"to":"01000000003","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488006","buttons":[{"buttonName":"앱 링크","buttonType":"AL","linkIos":"https://#{url}","linkAnd":"http://#{url}"},{"buttonName":"웹 링크","buttonType":"WL","linkMo":"https://www.coolsms.co.kr"},{"buttonName":"배송조회","buttonType":"DS"},{"buttonName":"키워드","buttonType":"BK"},{"buttonName":"전달","buttonType":"MD"}]}}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000003",
      "from": "029302266",
      "text": "#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.",
      "type": "ATA",
      "kakaoOptions": {
        "pfId": "KA01PF190227072057634pRBhbpAw1w1",
        "templateId": "test_2019030716320324334488006",
        "buttons": [
          {
            "buttonName": "앱 링크",
            "buttonType": "AL",
            "linkIos": "https://#{url}",
            "linkAnd": "http://#{url}"
          },
          {
            "buttonName": "웹 링크",
            "buttonType": "WL",
            "linkMo": "https://www.coolsms.co.kr"
          },
          {
            "buttonName": "배송조회",
            "buttonType": "DS"
          },
          {
            "buttonName": "키워드",
            "buttonType": "BK"
          },
          {
            "buttonName": "전달",
            "buttonType": "MD"
          }
        ]
      }
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"to":"01000000003","from":"029302266","text":"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.","type":"ATA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1","templateId":"test_2019030716320324334488006","buttons":[{"buttonName":"앱 링크","buttonType":"AL","linkIos":"https://#{url}","linkAnd":"http://#{url}"},{"buttonName":"웹 링크","buttonType":"WL","linkMo":"https://www.coolsms.co.kr"},{"buttonName":"배송조회","buttonType":"DS"},{"buttonName":"키워드","buttonType":"BK"},{"buttonName":"전달","buttonType":"MD"}]}}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"to\":\"01000000003\",\"from\":\"029302266\",\"text\":\"#{홍길동}님이 요청하신 출금 요청 처리가 완료되어 아래 정보로 입금 처리되었습니다.\n\n#{입금정보}\n\n관련하여 문의 있으시다면'1:1문의하기'를이용부탁드립니다.\n\n감사합니다.\",\"type\":\"ATA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\",\"templateId\":\"test_2019030716320324334488006\",\"buttons\":[{\"buttonName\":\"앱 링크\",\"buttonType\":\"AL\",\"linkIos\":\"https://#{url}\",\"linkAnd\":\"http://#{url}\"},{\"buttonName\":\"웹 링크\",\"buttonType\":\"WL\",\"linkMo\":\"https://www.coolsms.co.kr\"},{\"buttonName\":\"배송조회\",\"buttonType\":\"DS\"},{\"buttonName\":\"키워드\",\"buttonType\":\"BK\"},{\"buttonName\":\"전달\",\"buttonType\":\"MD\"}]}}]}";

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

##### 친구톡(CTA) 추가

> **Sample Request**

```json
{
    "messages": [
        {
            "to": "01000000004",
            "from": "029302266",
            "text": "cta test message",
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
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000004",
            "from": "029302266",
            "type": "CTA",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301QG8YG1XELCR66ZX",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        to: '01000000004',
        from: '029302266',
        text: 'cta test message',
        type: 'CTA',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1'
        }
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
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
    messages: [
      {
        to: '01000000004',
        from: '029302266',
        text: 'cta test message',
        type: 'CTA',
        kakaoOptions: {
          pfId: 'KA01PF190227072057634pRBhbpAw1w1'
        }
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
$data = '{"messages":[{"to":"01000000004","from":"029302266","text":"cta test message","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000004","from":"029302266","text":"cta test message","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}'

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
	-d '{"messages":[{"to":"01000000004","from":"029302266","text":"cta test message","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000004",
      "from": "029302266",
      "text": "cta test message",
      "type": "CTA",
      "kakaoOptions": {
        "pfId": "KA01PF190227072057634pRBhbpAw1w1"
      }
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"to":"01000000004","from":"029302266","text":"cta test message","type":"CTA","kakaoOptions":{"pfId":"KA01PF190227072057634pRBhbpAw1w1"}}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PFASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"to\":\"01000000004\",\"from\":\"029302266\",\"text\":\"cta test message\",\"type\":\"CTA\",\"kakaoOptions\":{\"pfId\":\"KA01PF190227072057634pRBhbpAw1w1\"}}]}";

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

##### to가 String일 경우

> **Sample Request**

```json
{
    "messages": [
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "test message",
            "autoTypeDetect": true
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143301PWELUIHJTAFOM98",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: 'test message',
        autoTypeDetect: true
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
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
    messages: [
      {
        to: '01000000001',
        from: '029302266',
        text: 'test message',
        autoTypeDetect: true
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
$data = '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","autoTypeDetect":true}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","autoTypeDetect":true}]}'

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
	-d '{"messages":[{"to":"01000000001","from":"029302266","text":"test message","autoTypeDetect":true}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": "01000000001",
      "from": "029302266",
      "text": "test message",
      "autoTypeDetect": true
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"to":"01000000001","from":"029302266","text":"test message","autoTypeDetect":true}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"to\":\"01000000001\",\"from\":\"029302266\",\"text\":\"test message\",\"autoTypeDetect\":true}]}";

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

##### to가 Array일 경우

> **Sample Request**

```json
{
    "messages": [
        {
            "to": [
                "01000000001",
                "01000000002"
            ],
            "from": "029302266",
            "text": "test message",
            "autoTypeDetect": true
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143303RMSFEOLL1ES1UPQ",
            "statusCode": "2000",
            "accountId": "12925149"
        },
        {
            "to": "01000000002",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143303FPCMYBW104H7MMR",
            "statusCode": "2000",
            "accountId": "12925149"
        }
    ]
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
    messages: [
      {
        to: ['01000000001', '01000000002'],
        from: '029302266',
        text: 'test message',
        autoTypeDetect: true
      }
    ]
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
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
    messages: [
      {
        to: ['01000000001', '01000000002'],
        from: '029302266',
        text: 'test message',
        autoTypeDetect: true
      }
    ]
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
$data = '{"messages":[{"to":["01000000001","01000000002"],"from":"029302266","text":"test message","autoTypeDetect":true}]}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":[{"to":["01000000001","01000000002"],"from":"029302266","text":"test message","autoTypeDetect":true}]}'

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
	-d '{"messages":[{"to":["01000000001","01000000002"],"from":"029302266","text":"test message","autoTypeDetect":true}]}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": [
    {
      "to": [
        "01000000001",
        "01000000002"
      ],
      "from": "029302266",
      "text": "test message",
      "autoTypeDetect": true
    }
  ]
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":[{"to":["01000000001","01000000002"],"from":"029302266","text":"test message","autoTypeDetect":true}]}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
    String parameters = "{\"messages\":[{\"to\":[\"01000000001\",\"01000000002\"],\"from\":\"029302266\",\"text\":\"test message\",\"autoTypeDetect\":true}]}";

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

##### to가 String인 경우와 Array인 경우가 합쳐진 경우

> **Sample Request**

```json
{
    "messages": [
        {
            "to": [
                "01000000001",
                "01000000002"
            ],
            "from": "029302266",
            "text": "test message",
            "autoTypeDetect": true
        },
        {
            "to": "01000000001",
            "from": "029302266",
            "text": "test message",
            "autoTypeDetect": true
        }
    ]
}
```

> **Sample Response**

```json
{
    "errorCount": 1,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143304SBHXXWZDOHCDH4L",
            "statusCode": "2000",
            "accountId": "12925149"
        },
        {
            "to": "01000000002",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "정상 접수(이통사로 접수 예정) ",
            "country": "82",
            "messageId": "M4V20190726143304UOQRRBRPKH5WQGI",
            "statusCode": "2000",
            "accountId": "12925149"
        },
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",
            "statusMessage": "중복 수신번호",
            "country": "82",
            "messageId": "M4V20190726143304WSV9IB674COIMNF",
            "statusCode": "1026",
            "accountId": "12925149"
        }
    ]
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
    messages: '[object Object],[object Obj...'
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
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
    messages: '[object Object],[object Obj...'
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
$data = '{"messages":"[object Object],[object Obj..."}';

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

url = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"messages":"[object Object],[object Obj..."}'

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
	-d '{"messages":"[object Object],[object Obj..."}' \
	http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "messages": "[object Object],[object Obj..."
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages"
  data := strings.NewReader(`{"messages":"[object Object],[object Obj..."}`)

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20190607105937H3PTASXMNJG2JID/messages";
    String parameters = "{\"messages\":\"[object Object],[object Obj...\"}";

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

