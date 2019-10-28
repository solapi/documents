# 발신번호 업데이트

## Request
```
PUT https://api.solapi.com/senderid/v1/numbers/:phoneNumber
```

발신번호 상태를 'ACTIVE'에서 'INACTIVE' 혹은 'INACTIVE' 에서 'ACTIVE'로 변경합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `senderid:read` | `role-senderid:read` |  |  |  |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :phoneNumber | 핸드폰 번호 |

### Request Structure
```json
{
    "status": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| status | `string` | O | 상태값 |


---

## Samples

### updateSenderId.spec.js

> **Sample Request**

```json
{
    "status": "INACTIVE"
}
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
            "status": "INACTIVE",
            "expireAt": null,
            "method": null,
            "log": [
                {
                    "createAt": "2019-10-28T17:59:25.457Z",
                    "message": "발신번호 상태를 'INACTIVE'로 변경하였습니다."
                }
            ],
            "dateCreated": "2019-10-28T17:59:25.446Z",
            "dateUpdated": "2019-10-28T17:59:25.457Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX2",
            "phoneNumber": "01000000000"
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
            "status": "PENDING",
            "expireAt": null,
            "method": null,
            "log": [],
            "dateCreated": "2019-10-28T17:59:25.445Z",
            "dateUpdated": "2019-10-28T17:59:25.445Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX3",
            "phoneNumber": "01000000001"
        }
    ],
    "limitationDocuments": [],
    "dateCreated": "2019-10-28T17:59:25.446Z",
    "dateUpdated": "2019-10-28T17:59:25.457Z"
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    status: 'INACTIVE'
  },
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/senderid/v1/numbers/01000000000'
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    status: 'INACTIVE'
  },
  method: 'PUT',
  url: 'http://api.solapi.com/senderid/v1/numbers/01000000000'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/senderid/v1/numbers/01000000000";
$data = '{"status":"INACTIVE"}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
        'content' => $data,
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

url = "http://api.solapi.com/senderid/v1/numbers/01000000000"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"status":"INACTIVE"}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"status":"INACTIVE"}' \
	http://api.solapi.com/senderid/v1/numbers/01000000000
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/numbers/01000000000")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "status": "INACTIVE"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Put.new(uri.request_uri, headers)
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
  uri := "http://api.solapi.com/senderid/v1/numbers/01000000000"
  data := strings.NewReader(`{"status":"INACTIVE"}`)

  req, err := http.NewRequest("PUT", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")
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
    String targetUrl = "http://api.solapi.com/senderid/v1/numbers/01000000000";
    String parameters = "{\"status\":\"INACTIVE\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");
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

> 문서 생성일 : 2019-10-28

