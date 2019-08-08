# 발신번호 중복 해제 요청

## Request

```text
POST https://api.solapi.com/senderid/v1/papers/duplicate/:phoneNumber
```

발신번호 상태가 중복\('DUPLICATED'\)일 경우 중복 해제를 위한 요청입니다.

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
    "reason": "string",
    "name": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| reason | `string` | O | 중복 해제 이유 |
| name | `string` |  | 이름 |

## Samples

### 정상

> **Sample Request**

```javascript
{
    "reason": "부서에 따른 아이디 할당을 위해 필요"
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
                "duplicateId": "DUP20190726162623DFPM3URAHAEGVI8",
                "reason": null,
                "reasonForRequested": "부서에 따른 아이디 할당을 위해 필요",
                "name": null,
                "status": "PENDING",
                "dateCreated": "2019-07-26T07:26:23.885Z",
                "dateUpdated": "2019-07-26T07:26:23.885Z"
            },
            "status": "PENDING",
            "expireAt": null,
            "method": null,
            "log": [
                {
                    "createAt": "2019-07-26T07:26:23.886Z",
                    "message": "중복 해제 요청을 하였습니다.\n담당자명: undefined\n사유: 부서에 따른 아이디 할당을 위해 필요"
                }
            ],
            "dateCreated": "2019-07-26T07:26:23.878Z",
            "dateUpdated": "2019-07-26T07:26:23.886Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX2",
            "phoneNumber": "01000000000"
        }
    ],
    "limitationDocuments": [],
    "dateCreated": "2019-07-26T07:26:23.879Z",
    "dateUpdated": "2019-07-26T07:26:23.886Z"
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
    reason: '부서에 따른 아이디 할당을 위해 필요'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/senderid/v1/papers/duplicate/01000000000'
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
    reason: '부서에 따른 아이디 할당을 위해 필요'
  },
  method: 'POST',
  url: 'http://api.solapi.com/senderid/v1/papers/duplicate/01000000000'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/senderid/v1/papers/duplicate/01000000000";
$data = '{"reason":"부서에 따른 아이디 할당을 위해 필요"}';

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

url = "http://api.solapi.com/senderid/v1/papers/duplicate/01000000000"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"reason":"부서에 따른 아이디 할당을 위해 필요"}'

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
    -d '{"reason":"부서에 따른 아이디 할당을 위해 필요"}' \
    http://api.solapi.com/senderid/v1/papers/duplicate/01000000000
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/papers/duplicate/01000000000")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "reason": "부서에 따른 아이디 할당을 위해 필요"
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
  uri := "http://api.solapi.com/senderid/v1/papers/duplicate/01000000000"
  data := strings.NewReader(`{"reason":"부서에 따른 아이디 할당을 위해 필요"}`)

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
    String targetUrl = "http://api.solapi.com/senderid/v1/papers/duplicate/01000000000";
    String parameters = "{\"reason\":\"부서에 따른 아이디 할당을 위해 필요\"}";

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

