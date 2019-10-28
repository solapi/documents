# 발신번호 인증

## Request
```
PUT https://api.solapi.com/senderid/v1/numbers/:phoneNumber/authenticate
```

넘어온 발신번호를 인증 후 활성화 처리합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `senderid:write` | `role-senderid:write` | `ACTIVE` | `ACTIVE` | O |

### 2차 인증 필요

| ARS 전화 인증 | 이메일 OTP |
| :---------: | :------: |
| O |  |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :phoneNumber | 핸드폰 번호 |

---

## Samples

### authenticateSenderId.spec.js

> **Sample Request**

```json
{}
```

> **Sample Response**

```json
{
    "limit": 2,
    "accountId": "12925149",
    "senderIds": [
        {
            "unlockDuplicate": {
                "duplicateId": null,
                "reason": null,
                "reasonForRequested": null,
                "name": null,
                "status": null,
                "dateCreated": null,
                "dateUpdated": null
            },
            "status": "PENDING",
            "expireAt": "2019-11-09T17:59:24.885Z",
            "method": null,
            "log": [],
            "dateCreated": "2019-10-28T17:59:25.370Z",
            "dateUpdated": "2019-10-28T17:59:25.370Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX3",
            "phoneNumber": "01000000001"
        },
        {
            "unlockDuplicate": {
                "duplicateId": null,
                "reason": null,
                "reasonForRequested": null,
                "name": null,
                "status": null,
                "dateCreated": null,
                "dateUpdated": null
            },
            "status": "ACTIVE",
            "expireAt": "2020-04-28T17:59:25.388Z",
            "method": "ARS",
            "log": [
                {
                    "createAt": "2019-10-28T17:59:25.389Z",
                    "message": "인증수단 'ARS'로 발신번호 인증이 완료되었습니다."
                }
            ],
            "dateCreated": "2019-10-28T17:59:25.370Z",
            "dateUpdated": "2019-10-28T17:59:25.389Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX2",
            "phoneNumber": "01000000000"
        }
    ],
    "limitationDocuments": [],
    "dateCreated": "2019-10-28T17:59:25.373Z",
    "dateUpdated": "2019-10-28T17:59:25.389Z"
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
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate'
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
  method: 'PUT',
  url: 'http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'PUT'
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

url = "http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.put(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Put.new(uri.request_uri, headers)

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
  uri := "http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate"

  req, err := http.NewRequest("PUT", uri, nil)
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
    String targetUrl = "http://api.solapi.com/senderid/v1/numbers/01000000000/authenticate";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

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

> 문서 생성일 : 2019-10-28

