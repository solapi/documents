# 시스템 발송 한도 증가 요청 목록 조회

## Request
```
GET https://api.solapi.com/quota/v1/me/system
```

시스템 발송 한도 증가 요청 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `quota:read` | `role-quota:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| status | `string` |  | eq | 상태값 |
| handleKey | `string` |  | eq | 각각 요청의 고유한 키 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |

---

## Samples

### 사용자 쿼터 증가 요청 목록 조회

> **Sample Request**

```
http://api.solapi.com/quota/v1/me/system?status=PENDING
```

> **Sample Response**

```json
{
    "limit": 20,
    "increaseQuotaList": [
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337403K1YHGoSUOLn",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.404Z",
            "dateUpdated": "2019-09-06T18:33:37.404Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337399WrE1T5liOdU",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.400Z",
            "dateUpdated": "2019-09-06T18:33:37.400Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337395kVEr7J2dQyV",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.396Z",
            "dateUpdated": "2019-09-06T18:33:37.396Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337392OpWq6ulT7Vq",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.392Z",
            "dateUpdated": "2019-09-06T18:33:37.392Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337388xHndQb8IBuy",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.389Z",
            "dateUpdated": "2019-09-06T18:33:37.389Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337385rKMPWdYbyYj",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.386Z",
            "dateUpdated": "2019-09-06T18:33:37.386Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337381MxHWCJxrVJE",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.382Z",
            "dateUpdated": "2019-09-06T18:33:37.382Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337378iXtmZq2UQUa",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.379Z",
            "dateUpdated": "2019-09-06T18:33:37.379Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337375SpH3GSwPh6q",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.375Z",
            "dateUpdated": "2019-09-06T18:33:37.375Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ1909061933373718diRlJfZ6uV",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.372Z",
            "dateUpdated": "2019-09-06T18:33:37.372Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337368pk8B9TB8cdN",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.368Z",
            "dateUpdated": "2019-09-06T18:33:37.368Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337364d22kWh4dDlA",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.365Z",
            "dateUpdated": "2019-09-06T18:33:37.365Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ1909061933373611lCiVsufxxs",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.361Z",
            "dateUpdated": "2019-09-06T18:33:37.361Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337357Qjid9XhGpok",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.358Z",
            "dateUpdated": "2019-09-06T18:33:37.358Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190906193337353uiclg0i0TTe",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-06T18:33:37.354Z",
            "dateUpdated": "2019-09-06T18:33:37.354Z"
        }
    ],
    "startKey": "QT01IQ190906193337403K1YHGoSUOLn",
    "nextKey": null
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
  url: 'http://api.solapi.com/quota/v1/me/system?status=PENDING'
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
  url: 'http://api.solapi.com/quota/v1/me/system?status=PENDING'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/quota/v1/me/system?status=PENDING";

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

url = "http://api.solapi.com/quota/v1/me/system?status=PENDING"
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
	http://api.solapi.com/quota/v1/me/system?status=PENDING
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/quota/v1/me/system?status=PENDING")

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
  uri := "http://api.solapi.com/quota/v1/me/system?status=PENDING"

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
    String targetUrl = "http://api.solapi.com/quota/v1/me/system?status=PENDING";

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

> 문서 생성일 : 2019-09-06

