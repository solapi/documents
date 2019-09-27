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
            "handleKey": "QT01IQ190927060836232mjIEn24RWss",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.233Z",
            "dateUpdated": "2019-09-27T05:08:36.233Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ1909270608362283xus68Wut2Z",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.229Z",
            "dateUpdated": "2019-09-27T05:08:36.229Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ1909270608362242U0O6d57ojd",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.225Z",
            "dateUpdated": "2019-09-27T05:08:36.225Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836220ITKnQUdmQb2",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.221Z",
            "dateUpdated": "2019-09-27T05:08:36.221Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836217G3E5wYEtUvC",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.218Z",
            "dateUpdated": "2019-09-27T05:08:36.218Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836213wPkHTtWUAuR",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.214Z",
            "dateUpdated": "2019-09-27T05:08:36.214Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836210YD5nDHi5Go8",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.211Z",
            "dateUpdated": "2019-09-27T05:08:36.211Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836206to6wNGgXBzc",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.207Z",
            "dateUpdated": "2019-09-27T05:08:36.207Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836203SR8yCfurnld",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.204Z",
            "dateUpdated": "2019-09-27T05:08:36.204Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836199Oe3iU449r9g",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.200Z",
            "dateUpdated": "2019-09-27T05:08:36.200Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ19092706083619624q8js16xrB",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.197Z",
            "dateUpdated": "2019-09-27T05:08:36.197Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836192fkQpt2Tc3I2",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.193Z",
            "dateUpdated": "2019-09-27T05:08:36.193Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836189w8LtCCQDzSt",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.190Z",
            "dateUpdated": "2019-09-27T05:08:36.190Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836185VT5HEKqwrV6",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.186Z",
            "dateUpdated": "2019-09-27T05:08:36.186Z"
        },
        {
            "status": "PENDING",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u211",
                "ST01FE190429073419477NoBqiP9u212"
            ],
            "reasonRequested": "오늘은 점심이 기대됩니다.",
            "reasonRejected": "오늘은 점심이 기대가 되지 않습니다.",
            "handleKey": "QT01IQ190927060836179ihyS2o8cpRl",
            "accountId": "19205486948963",
            "requestedQuota": 2524242,
            "dateCreated": "2019-09-27T05:08:36.180Z",
            "dateUpdated": "2019-09-27T05:08:36.180Z"
        }
    ],
    "startKey": "QT01IQ190927060836232mjIEn24RWss",
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

> 문서 생성일 : 2019-09-27

