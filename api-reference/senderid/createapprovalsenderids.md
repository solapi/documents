# 증빙자료 인증 요청

## Request

```text
POST https://api.solapi.com/senderid/v1/papers/approval/:phoneNumber
```

등록된 발신번호의 인증을 위해 증빙자료를 제출 합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `senderid:write` | `role-senderid:write` | `ACTIVE` |  | O |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :phoneNumber | 핸드폰 번호 |

### Request Structure

```javascript
{
    "documents": [
        "string"
    ]
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| documents | `Array` | O | 문서 ID 목록 |

## Samples

### 정상

> **Sample Request**

```javascript
{
    "documents": [
        "DOC20181030105615MMXDST163SYMMX3"
    ]
}
```

> **Sample Response**

```javascript
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
            "expireAt": null,
            "method": null,
            "log": [
                {
                    "createAt": "2019-07-26T07:26:23.770Z",
                    "message": "발신번호 증빙자료 요청을 하였습니다."
                }
            ],
            "dateCreated": "2019-07-26T07:26:23.746Z",
            "dateUpdated": "2019-07-26T07:26:23.770Z",
            "approvalDocuments": [
                {
                    "documents": [
                        "DOC20181030105615MMXDST163SYMMX3"
                    ],
                    "status": "PENDING",
                    "reason": null,
                    "dateCreated": "2019-07-26T07:26:23.771Z",
                    "dateUpdated": "2019-07-26T07:26:23.771Z",
                    "approvalId": "APD20190726162623XKDSXFCELQI2ACA"
                }
            ],
            "handleKey": "SED201810301056FFFFFFFFFFFFFFFFF",
            "phoneNumber": "01000000000"
        }
    ],
    "limitationDocuments": [],
    "dateCreated": "2019-07-26T07:26:23.747Z",
    "dateUpdated": "2019-07-26T07:26:23.771Z"
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    documents: 'DOC20181030105615MMXDST163S...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/senderid/v1/papers/approval/01000000000'
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
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    documents: 'DOC20181030105615MMXDST163S...'
  },
  method: 'POST',
  url: 'http://api.solapi.com/senderid/v1/papers/approval/01000000000'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/senderid/v1/papers/approval/01000000000";
$data = '{"documents":"DOC20181030105615MMXDST163S..."}';

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/senderid/v1/papers/approval/01000000000"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"documents":"DOC20181030105615MMXDST163S..."}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X POST \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    -H 'Content-Type: application/json' \
    -d '{"documents":"DOC20181030105615MMXDST163S..."}' \
    http://api.solapi.com/senderid/v1/papers/approval/01000000000
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/papers/approval/01000000000")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "documents": "DOC20181030105615MMXDST163S..."
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
  uri := "http://api.solapi.com/senderid/v1/papers/approval/01000000000"
  data := strings.NewReader(`{"documents":"DOC20181030105615MMXDST163S..."}`)

  req, err := http.NewRequest("POST", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")
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
    String targetUrl = "http://api.solapi.com/senderid/v1/papers/approval/01000000000";
    String parameters = "{\"documents\":\"DOC20181030105615MMXDST163S...\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");
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

