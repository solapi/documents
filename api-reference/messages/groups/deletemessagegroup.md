# 그룹 삭제

> 문서 생성일 : 2019-08-07

## 그룹 삭제

### Request

```text
DELETE https://api.solapi.com/messages/v4/groups/:groupId
```

메시지 그룹을 삭제합니다. 삭제 후 발송 및 복구가 불가합니다.

#### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `message:write` | `role-message:write` | `ACTIVE` | `ACTIVE` | O |

#### Path Parameters

| Name | Description |
| :---: | :---: |
| :groupId | 설명 없음 |

### Samples

#### 그룹 삭제

> **Sample Request**

```javascript
{}
```

> **Sample Response**

```javascript
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
            "createAt": "2019-08-07T06:59:13.052Z"
        },
        {
            "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.",
            "createAt": "2019-08-07T06:59:13.052Z"
        },
        {
            "createAt": "2019-08-07T06:59:19.099Z",
            "message": "메시지를 발송했습니다.",
            "oldBalance": 100,
            "newBalance": 100,
            "oldPoint": 100,
            "newPoint": 50,
            "totalPrice": 20
        },
        {
            "message": "메시지 그룹이 삭제되었습니다.",
            "createAt": "2019-08-07T06:59:19.460Z"
        }
    ],
    "status": "DELETED",
    "scheduledDate": null,
    "dateSent": "2019-08-07T06:59:19.099Z",
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
    "price": {
        "82": {
            "sms": 20,
            "lms": 50,
            "mms": 200,
            "ata": 19,
            "cta": 13
        }
    },
    "dateCreated": "2019-08-07T06:59:13.055Z",
    "dateUpdated": "2019-08-07T06:59:19.463Z"
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'DELETE',
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
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'DELETE',
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
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
        'method'  => 'DELETE'
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
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.delete(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X DELETE \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
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
  "Authorization": "Bearer eyJhbGciOiJI..."
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Delete.new(uri.request_uri, headers)

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

  req, err := http.NewRequest("DELETE", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")

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

    con.setRequestMethod("DELETE");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");

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
