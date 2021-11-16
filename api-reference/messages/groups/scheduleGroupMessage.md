# 발송 예약

## Request
```
POST https://api.solapi.com/messages/v4/groups/:groupId/schedule
```

그룹 메시지를 에약 처리합니다. 예약 상태에서 그룹내 메시지 추가 및 삭제가 불가합니다. 최대 6개월까지 접수 가능하며 발송 시점에 잔액이 차감되며 잔액이 없을 경우 발송 실패 처리됩니다.

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :groupId | 메시지 그룹 아이디 |

### Request Structure
```json
{
    "scheduledDate": "date"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| scheduledDate | `date` | O | 설명 없음 |


---

## Samples

### groups/scheduledGroupMessage

> **Sample Request**

```json
{
    "scheduledDate": "2021-11-16T05:12:39.157Z"
}
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
            "message": "메시지 그룹이 생성되었습니다.",
            "createAt": "2021-11-16T05:09:39.810Z"
        },
        {
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.",
            "createAt": "2021-11-16T05:09:39.810Z"
        },
        {
            "message": "발송 예정일이 6개월을 초과하여 발송 예약에 실패하였습니다.",
            "createAt": "2021-11-16T05:09:47.536Z"
        },
        {
            "createAt": "2021-11-16T05:09:47.559Z",
            "message": "메시지 예약이 성공적으로 접수됐습니다.",
            "messageCount": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 1
            }
        }
    ],
    "status": "SCHEDULED",
    "dateSent": null,
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": true,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20180307105937AAAAAASCHEDULED",
    "groupId": "G4V20180307105937AAAAAASCHEDULED",
    "accountId": "12925149",
    "apiVersion": "4",
    "price": {},
    "customFields": {},
    "hint": {},
    "dateCreated": "2021-11-16T05:09:39.812Z",
    "dateUpdated": "2021-11-16T05:09:47.560Z"
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    'Content-Type': 'application/json'
  },
  body: {
    scheduledDate: '2021-11-16T05:12:39.157Z'
  },
  method: 'POST',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule'
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
$url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule";
$data = '{"scheduledDate":"2021-11-16T05:12:39.157Z"}';

$options = array(
    'http' => array(
        'header'  => "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule"
headers = {
  "Content-Type": "application/json"
}
data = '{"scheduledDate":"2021-11-16T05:12:39.157Z"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Content-Type: application/json' \
	-d '{"scheduledDate":"2021-11-16T05:12:39.157Z"}' \
	http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule")

headers = {
  "Content-Type": "application/json"
}
data = {
  "scheduledDate": "2021-11-16T05:12:39.157Z"
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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule"
  data := strings.NewReader(`{"scheduledDate":"2021-11-16T05:12:39.157Z"}`)

  req, err := http.NewRequest("POST", uri, data)
  if err != nil { panic(err) }

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20180307105937AAAAAASCHEDULED/schedule";
    String parameters = "{\"scheduledDate\":\"2021-11-16T05:12:39.157Z\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

> 문서 생성일 : 2021-11-16

