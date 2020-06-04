# 웹훅 목록 조회

## Request

```text
GET https://api.solapi.com/webhook/v1/outgoing
```

등록된 웹훅 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `webhook:read` | `role-webhook:read` | `ACTIVE` |  | O |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| eventId | `string` |  | eq | 설명 없음 |
| url | `string` |  | eq | 설명 없음 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| status | `string` |  | eq | 상태값 |
| handleKey | `타입을 찾을 수 없음` |  | eq | 설명 없음 |
| dateCreated | `date` |  | gte, lte, gt, lt, eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | gte, lte, gt, lt, eq | 최근 수정 날짜 |

## Samples

### readOutgoingData.spec.js

> **Sample Request**

```text
http://api.solapi.com/webhook/v1/outgoing?
```

> **Sample Response**

```javascript
{
    "limit": 20,
    "webhookList": [
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851347o3SA6WESKbP",
            "eventId": "WH01ET1912300028513478YOxKqMnUmF",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851347gBTEPFVJ1dn",
            "eventId": "WH01ET191230002851347bKOGZ2usiIj",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851347G69NUYB8BRr",
            "eventId": "WH01ET191230002851347l1PJZpIZPZ9",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1912300028513476a1opHKGk6d",
            "eventId": "WH01ET191230002851347JqxqnTsy3VM",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "INACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH1912300028513471KKhQNq2vzg",
            "eventId": "WH01ET191230002851347an278qBzDKI",
            "url": "https://solapi.com/report1",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346z1MkJtgB5az",
            "eventId": "WH01ET191230002851346CNEdQDkJR2s",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346xhJjHZjME8U",
            "eventId": "WH01ET191230002851346EVlITFJu8GA",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346q4JINA88GTA",
            "eventId": "WH01ET191230002851346AondKt9lMqc",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346ohNBXVrUAgh",
            "eventId": "WH01ET191230002851346BF0404R1okn",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346VmWZO0mycX9",
            "eventId": "WH01ET191230002851346mUAyDTDYtkg",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346VST9DgFBZUF",
            "eventId": "WH01ET191230002851347w0ncgEr8Vo1",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.368Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346MWb8GZAK4kG",
            "eventId": "WH01ET191230002851346BNgd5QmRZPh",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851346GhYzFVwtmSa",
            "eventId": "WH01ET191230002851346OvR7ds1bxD6",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.368Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH19123000285134603jekGpc8lq",
            "eventId": "WH01ET1912300028513461Fxnrac4D5r",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345rXrkiemWy4A",
            "eventId": "WH01ET191230002851345dQ01oQOwjJT",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.366Z",
            "dateUpdated": "2019-12-30T00:28:51.366Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345fCWx1Q4GJJV",
            "eventId": "WH01ET191230002851345QcfF7YknKoo",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345cUeTCdNULC0",
            "eventId": "WH01ET1912300028513450ELOaVRlgpO",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345XqwzGp0WLQQ",
            "eventId": "WH01ET191230002851345FjYAKchRfvS",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.367Z",
            "dateUpdated": "2019-12-30T00:28:51.367Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345VhRe8VwMupy",
            "eventId": "WH01ET191230002851345pIWpYdaY5Cy",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.366Z",
            "dateUpdated": "2019-12-30T00:28:51.366Z"
        },
        {
            "secret": null,
            "status": "ACTIVE",
            "failCount": 0,
            "accountId": "12925149",
            "webhookId": "WH01WH191230002851345H8eYG4KNHMD",
            "eventId": "WH01ET191230002851345lVH7RzsgJgq",
            "url": "https://solapi.com/report",
            "dateCreated": "2019-12-30T00:28:51.366Z",
            "dateUpdated": "2019-12-30T00:28:51.366Z"
        }
    ],
    "startKey": "WH01WH191230002851347o3SA6WESKbP",
    "nextKey": "WH01WH191230002851345C1pNcKNv6oJ"
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
```text
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

> 문서 생성일 : 2019-12-30

