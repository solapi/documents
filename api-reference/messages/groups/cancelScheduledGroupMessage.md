# 예약 취소

#### Request
```
DELETE https://api.solapi.com/messages/v4/groups/:groupId/schedule
```

예약된 그룹을 취소 처리하고 'PENDING'상태로 변경합니다. 예약 취소된 그룹은 다시 예약하거나 발송 요청하지 않는 한 발송 처리되지 않습니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:write` | `role-message:write` | `ACTIVE` | `ACTIVE` | O |

##### Path Parameters

| Name | Description |
| :--: | :---------: |
| :groupId | 설명 없음 |

---

#### Samples

##### 예약 취소

> **Sample Request**

```
{}
```

> **Sample Response**

```json
{
    "_id": "G4V20180307105937CANCELSCHEDULED",
    "count": {
        "total": 0,
        "sentTotal": 0,
        "sentFailed": 0,
        "sentSuccess": 0,
        "sentPending": 0,
        "sentReplacement": 0,
        "refund": 0,
        "registeredFailed": 0,
        "registeredSuccess": 0
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
            "createAt": "2019-08-01T23:00:35.800Z",
            "message": "메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2019-08-01T23:00:41.045Z",
            "message": "메시지 예약이 성공적으로 취소됐습니다."
        }
    ],
    "status": "PENDING",
    "scheduledDate": null,
    "dateSent": null,
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "groupId": "G4V20180307105937CANCELSCHEDULED",
    "accountId": "12925149",
    "apiVersion": "4",
    "countForCharge": {
        "sms": {
            "82": 0
        },
        "lms": {},
        "mms": {},
        "ata": {},
        "cta": {}
    },
    "price": {},
    "dateCreated": "2019-08-01T23:00:35.803Z",
    "dateUpdated": "2019-08-01T23:00:41.045Z"
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
    'http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule'
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
    'http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule";

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

url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.delete(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X DELETE \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule")

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
  uri := "http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule"

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule";

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

---

