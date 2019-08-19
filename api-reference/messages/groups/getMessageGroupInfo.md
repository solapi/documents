> 문서 생성일 : 2019-08-19

# 그룹 정보 조회

#### Request
```
GET https://api.solapi.com/messages/v4/groups/:groupId
```

메시지 그룹의 정보를 조회합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` | O |

##### Path Parameters

| Name | Description |
| :--: | :---------: |
| :groupId | 설명 없음 |

---

#### Response

##### Response Structure
```json
{
    "count": {
        "total": "number",
        "sentTotal": "number",
        "sentFailed": "number",
        "sentSuccess": "number",
        "sentPending": "number",
        "sentReplacement": "number",
        "refund": "number",
        "registeredFailed": "number",
        "registeredSuccess": "number"
    },
    "balance": {
        "requested": "number",
        "replacement": "number",
        "refund": "number",
        "sum": "number"
    },
    "point": {
        "requested": "number",
        "replacement": "number",
        "refund": "number",
        "sum": "number"
    },
    "app": {
        "profit": {
            "sms": "number",
            "lms": "number",
            "mms": "number",
            "ata": "number",
            "cta": "number"
        },
        "appId": "string",
        "version": "string"
    },
    "sdkVersion": "string",
    "osPlatform": "string",
    "log": [
        {
            "message": "object",
            "createAt": "date"
        }
    ],
    "status": "string",
    "scheduledDate": "date",
    "dateSent": "date",
    "dateCompleted": "date",
    "isRefunded": "boolean",
    "flagUpdated": "boolean",
    "groupId": "string",
    "accountId": "string",
    "apiVersion": "string",
    "countForCharge": {
        "sms": {
            "country": "number"
        },
        "lms": {
            "country": "number"
        },
        "mms": {
            "country": "number"
        },
        "ata": {
            "country": "number"
        },
        "cta": {
            "country": "number"
        }
    },
    "price": {},
    "dateCreated": "date",
    "dateUpdated": "date"
}
```

##### Response Description
##### Response / 

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [count](#response-count) | `object` |  | 카운트 |
| [balance](#response-balance) | `number` |  | 잔액 |
| [point](#response-point) | `number` |  | 포인트 |
| [app](#response-app) | `object` |  | 앱 정보 |
| sdkVersion | `string` |  | SDK 버전 |
| osPlatform | `string` |  | OS / Platform |
| [log](#response-log) | `Array` |  | 로그 |
| status | `string` |  | 그룹 상태<br>PENDING - 대기중<br>SENDING - 이미 발송 요청된 그룹<br>DELETED - 삭제 처리된 그룹<br>FAILED - 실패 처리된 그룹<br>SCHEDULED - 발송 예약된 그룹<br>COMPLETE - 발송 완료된 그룹 |
| scheduledDate | `date` |  | 예약 일시 |
| dateSent | `date` |  | 발송 일시 |
| dateCompleted | `date` |  | 완료 일시 |
| isRefunded | `boolean` |  | 환급 여부 |
| flagUpdated | `boolean` |  | 업데이트 여부 |
| groupId | `string` |  | 그룹 아이디 |
| accountId | `string` |  | 계정 고유 번호 |
| apiVersion | `string` |  | API 버전 |
| [countForCharge](#response-countforcharge) | `object` |  | 차감 카운트 |
| [price](#response-price) | `object` |  | 단가 |
| dateCreated | `date` |  | 생성 일시 |
| dateUpdated | `date` |  | 업데이트 일시 |

##### Response / count

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| total | `number` |  | 토탈 |
| sentTotal | `number` |  | 전체 발송 건수 |
| sentFailed | `number` |  | 발송 실패 건수 |
| sentSuccess | `number` |  | 발송 성공 건수 |
| sentPending | `number` |  | 대기 건수 |
| sentReplacement | `number` |  | 대체 발송 건수 |
| refund | `number` |  | 환급 건수 |
| registeredFailed | `number` |  | 접수 실패 건수 |
| registeredSuccess | `number` |  | 접수 성공 건수 |

##### Response / balance

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| requested | `number` |  | 차감 금액 |
| replacement | `number` |  | 대체 발송 금액 |
| refund | `number` |  | 환급 금액 |
| sum | `number` |  | 합계 금액 |

##### Response / point

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| requested | `number` |  | 차감 포인트 |
| replacement | `number` |  | 대체 발송 포인트 |
| refund | `number` |  | 환급 포인트 |
| sum | `number` |  | 합계 포인트 |

##### Response / app

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [profit](#response-app-profit) | `object` |  | 앱 사용 요금 |
| appId | `string` |  | 앱 아이디 |
| version | `string` |  | 설명 없음 |

##### Response / app / profit

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| sms | `number` |  | SMS 사용 요금 |
| lms | `number` |  | LMS 사용 요금 |
| mms | `number` |  | MMS 사용 요금 |
| ata | `number` |  | 알림톡 사용 요금 |
| cta | `number` |  | 친구톡 사용 요금 |


##### Response / log

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| message | `object` |  | 로그 메시지 |
| createAt | `date` |  | 로그 기록 일시 |

##### Response / countForCharge

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [sms](#response-countforcharge-sms) | `object` |  | SMS 차감 금액 |
| [lms](#response-countforcharge-lms) | `object` |  | LMS 차감 금액 |
| [mms](#response-countforcharge-mms) | `object` |  | MMS 차감 금액 |
| [ata](#response-countforcharge-ata) | `object` |  | 알림톡 차감 금액 |
| [cta](#response-countforcharge-cta) | `object` |  | 친구톡 차감 금액 |

##### Response / countForCharge / sms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 SMS 차감 금액 |

##### Response / countForCharge / lms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 LMS 차감 금액 |

##### Response / countForCharge / mms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 MMS 차감 금액 |

##### Response / countForCharge / ata

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 알림톡 차감 금액 |

##### Response / countForCharge / cta

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 친구톡 차감 금액 |

##### Response / price

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |


---

#### Samples

##### 메시지 그룹 정보 get /messages/v4/groups/:groupId

> **Sample Request**

```
http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
```

> **Sample Response**

```json
{
    "count": {
        "total": 0,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 1
    },
    "balance": {
        "requested": 0,
        "replacement": 0,
        "refund": 0,
        "sum": 0
    },
    "point": {
        "requested": 0,
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
            "cta": 0
        },
        "appId": null,
        "version": null
    },
    "sdkVersion": null,
    "osPlatform": null,
    "log": [
        {
            "message": "메시지 그룹이 생성되었습니다.",
            "createAt": "2019-08-19T07:33:08.065Z"
        },
        {
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.",
            "createAt": "2019-08-19T07:33:08.065Z"
        }
    ],
    "status": "PENDING",
    "scheduledDate": null,
    "dateSent": null,
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "_id": "G4V20180307105937H3PTASXMNJG2JIO",
    "groupId": "G4V20180307105937H3PTASXMNJG2JIO",
    "accountId": "12925149",
    "apiVersion": "4",
    "countForCharge": {
        "sms": {
            "82": 1
        },
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {}
    },
    "price": {},
    "dateCreated": "2019-08-19T07:33:08.076Z",
    "dateUpdated": "2019-08-19T07:33:08.076Z"
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO'
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'GET'
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

url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, headers)

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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");

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

