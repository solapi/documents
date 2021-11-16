# 메시지 예약 취소

## Request
```
DELETE https://api.solapi.com/messages/v4/groups/:groupId/schedule
```

예약된 메시지를 취소 처리하고 그룹을 'FAILED'상태로 변경합니다.

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :groupId | 메시지 그룹 아이디 |

---

## Samples

### groups/cancelScheduledGroupMessage

> **Sample Request**

```json
{}
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
        "registeredSuccess": 0
    },
    "countForCharge": {
        "sms": {},
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
            "createAt": "2021-11-16T05:09:39.814Z",
            "message": "메시지 그룹이 생성되었습니다."
        },
        {
            "createAt": "2021-11-16T05:09:47.680Z",
            "message": "메시지 예약이 성공적으로 취소됐습니다."
        }
    ],
    "status": "FAILED",
    "dateSent": null,
    "dateCompleted": null,
    "isRefunded": false,
    "flagUpdated": false,
    "prepaid": true,
    "strict": true,
    "masterAccountId": null,
    "allowDuplicates": false,
    "_id": "G4V20180307105937CANCELSCHEDULED",
    "groupId": "G4V20180307105937CANCELSCHEDULED",
    "accountId": "12925149",
    "apiVersion": "4",
    "price": {},
    "customFields": {},
    "hint": {},
    "dateCreated": "2021-11-16T05:09:39.816Z",
    "dateUpdated": "2021-11-16T05:09:47.681Z"
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
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

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule";

$options = array(
    'http' => array(
        'header'  => ,
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

response = requests.delete(url)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X DELETE \
	http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/G4V20180307105937CANCELSCHEDULED/schedule")

http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Delete.new(uri.request_uri, )

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

