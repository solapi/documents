# 웹훅 목록 조회

## Request
```
GET https://api.solapi.com/webhook/v1/outgoing
```

등록된 웹훅 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `webhook:read` | `role-webhook:read` | `ACTIVE` |  | O |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| url | `string` |  | eq | 설명 없음 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| status | `string` |  | eq | 상태값 |
| handleKey | `타입을 찾을 수 없음` |  | eq | 설명 없음 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |

---

## Samples

### readOutgoingData.spec.js

> **Sample Request**

```
http://api.solapi.com/webhook/v1/outgoing?
```

> **Sample Response**

```json
{
    "limit": 20,
    "webhookList": [
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143948VqdSDPzKDWG",
            "eventId": "WH01ET191030195143948WNRK4jUVdmt",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143948SvXzJVv1ZeY",
            "eventId": "WH01ET191030195143948eYDs7Y81ROl",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947uKcR57xKpQg",
            "eventId": "WH01ET191030195143947sxLxFSzfPRr",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947sA8ejwvQGQy",
            "eventId": "WH01ET191030195143947eyqKsGrmgL5",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947iFB4xRfd9Ki",
            "eventId": "WH01ET191030195143947yx1Of0hnbdw",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947gSLhyEwbQYU",
            "eventId": "WH01ET191030195143947zLZVjmbJalO",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947dpIB8qb1mpH",
            "eventId": "WH01ET191030195143947yq1gEhMn6Nj",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947ZmJ5oIAUxdj",
            "eventId": "WH01ET191030195143947KZartUDO6pt",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947YHsKBV2uQR6",
            "eventId": "WH01ET1910301951439479zGUSSbNabA",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947SOFQQSn2Fah",
            "eventId": "WH01ET191030195143947odwbmpHmRUp",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947MopMcihsEj4",
            "eventId": "WH01ET191030195143947OI7khBxCwUg",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143947HDB1IemjrMp",
            "eventId": "WH01ET191030195143947f2ujOWgVzkV",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910301951439479XCRZMqpcW7",
            "eventId": "WH01ET1910301951439485oYh50AcUpH",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-10-30T19:51:43.971Z",
            "dateUpdated": "2019-10-30T19:51:43.971Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1910301951439476vYVBatjchs",
            "eventId": "WH01ET191030195143947MAxpwP4n0Yn",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946uRvoNG6IfVt",
            "eventId": "WH01ET191030195143946NskMQGAgZc4",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.969Z",
            "dateUpdated": "2019-10-30T19:51:43.969Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946q3iF7Ab4nWf",
            "eventId": "WH01ET191030195143946LR044U81LCx",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.968Z",
            "dateUpdated": "2019-10-30T19:51:43.968Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946cljwwGRSvGu",
            "eventId": "WH01ET1910301951439464Sd1c46iGc9",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.969Z",
            "dateUpdated": "2019-10-30T19:51:43.969Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946ZSkBkPcakqn",
            "eventId": "WH01ET191030195143946ugFqaOpdiis",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.969Z",
            "dateUpdated": "2019-10-30T19:51:43.969Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946WoKMFOj4O3D",
            "eventId": "WH01ET191030195143946jSKuVtfAmm2",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.970Z",
            "dateUpdated": "2019-10-30T19:51:43.970Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191030195143946KdFjNHZZy1w",
            "eventId": "WH01ET1910301951439464AuWwlR639W",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-10-30T19:51:43.969Z",
            "dateUpdated": "2019-10-30T19:51:43.969Z"
        }
    ],
    "startKey": "WH01WH191030195143948VqdSDPzKDWG",
    "nextKey": "WH01WH191030195143946I5IFYdQVjX1"
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
  url: 'http://api.solapi.com/webhook/v1/outgoing?'
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
  url: 'http://api.solapi.com/webhook/v1/outgoing?'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/webhook/v1/outgoing?";

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

url = "http://api.solapi.com/webhook/v1/outgoing?"
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
	http://api.solapi.com/webhook/v1/outgoing?
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/webhook/v1/outgoing?")

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
  uri := "http://api.solapi.com/webhook/v1/outgoing?"

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
    String targetUrl = "http://api.solapi.com/webhook/v1/outgoing?";

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

> 문서 생성일 : 2019-10-30

