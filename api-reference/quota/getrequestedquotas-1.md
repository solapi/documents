# 시스템 발송 한도 증가 요청 목록 조회

## Request

```text
GET https://api.solapi.com/quota/v1/me/system
```

시스템 발송 한도 증가 요청 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `quota:read` | `role-quota:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| status | `string` |  | eq | 상태값 |
| handleKey | `string` |  | eq | 각각 요청의 고유한 키 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최근 수정 날짜 |

## Samples

### 사용자 쿼터 증가 요청 목록 조회

> **Sample Request**

```text
http://api.solapi.com/quota/v1/me/system?status=APPROVED
```

> **Sample Response**

```javascript
{
    "limit": 20,
    "increaseQuotaList": [
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031829XykGqyomJBc",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.830Z",
            "dateUpdated": "2019-12-30T00:00:31.830Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031826EAw9cSa8QQv",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.826Z",
            "dateUpdated": "2019-12-30T00:00:31.826Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031822s3hICoHgPuZ",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.822Z",
            "dateUpdated": "2019-12-30T00:00:31.822Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ1912300000318188XYaBrN42s8",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.819Z",
            "dateUpdated": "2019-12-30T00:00:31.819Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031815iJbZxZ8GBsn",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.816Z",
            "dateUpdated": "2019-12-30T00:00:31.816Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031811Ww8yX6KSgXx",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.812Z",
            "dateUpdated": "2019-12-30T00:00:31.812Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031808q9eITKpYmzx",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.809Z",
            "dateUpdated": "2019-12-30T00:00:31.809Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031804wXg9s999tmR",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.805Z",
            "dateUpdated": "2019-12-30T00:00:31.805Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031801goDdo7k73Iq",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.801Z",
            "dateUpdated": "2019-12-30T00:00:31.801Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031797eQpwVx0TJoz",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.798Z",
            "dateUpdated": "2019-12-30T00:00:31.798Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031793EhTRDfeLVbs",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.794Z",
            "dateUpdated": "2019-12-30T00:00:31.794Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031790iNw4A4vIwlP",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.790Z",
            "dateUpdated": "2019-12-30T00:00:31.790Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031786bFi8qUIDo4g",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.787Z",
            "dateUpdated": "2019-12-30T00:00:31.787Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031782vy6mIs0tRbH",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.783Z",
            "dateUpdated": "2019-12-30T00:00:31.783Z"
        },
        {
            "status": "APPROVED",
            "fileIds": [
                "ST01FE190429073419477NoBqiP9u111",
                "ST01FE190429073419477NoBqiP9u112"
            ],
            "reasonRequested": "오늘은 날씨가 정말 좋습니다.",
            "reasonRejected": "오늘은 날씨가 정말 안 좋습니다.",
            "handleKey": "QT01IQ191230000031772nt08941l1nJ",
            "accountId": "19205486948203",
            "requestedQuota": 100000,
            "dateCreated": "2019-12-30T00:00:31.778Z",
            "dateUpdated": "2019-12-30T00:00:31.778Z"
        }
    ],
    "startKey": "QT01IQ191230000031829XykGqyomJBc",
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
  url: 'http://api.solapi.com/quota/v1/me/system?status=APPROVED'
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
$url = "http://api.solapi.com/quota/v1/me/system?status=APPROVED";

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

url = "http://api.solapi.com/quota/v1/me/system?status=APPROVED"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X GET \
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    http://api.solapi.com/quota/v1/me/system?status=APPROVED
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/quota/v1/me/system?status=APPROVED")

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
  uri := "http://api.solapi.com/quota/v1/me/system?status=APPROVED"

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
    String targetUrl = "http://api.solapi.com/quota/v1/me/system?status=APPROVED";

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

> 문서 생성일 : 2019-12-30

