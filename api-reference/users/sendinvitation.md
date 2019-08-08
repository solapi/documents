# 초대장 발송

## Request

```text
POST https://api.solapi.com/users/v1/invitations
```

관리자\(OWNER\)가 특정 이메일로 초대장을 발송합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `accounts:write` | `role-accounts:write` | `ACTIVE` | `ACTIVE` | O |

### Request Structure

```javascript
{
    "email": "email",
    "role": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| email | `email` | O | 이메일 |
| role | `string` | O | 권한 \(OWNER, DEVELOPER, MEMBER\) |

## Samples

### 정상

> **Sample Request**

```javascript
{
    "email": "newMail@test.net",
    "role": "DEVELOPER"
}
```

> **Sample Response**

```javascript
{
    "mail": {
        "accepted": [
            "newMail@test.net"
        ],
        "rejected": [],
        "envelopeTime": 824,
        "messageTime": 604,
        "messageSize": 477,
        "response": "250 Accepted [STATUS=new MSGID=XCm9j2EZlw0y9P3eXT-trCAaGyvGgLqkAAAdZdIq4G3CVMWl0CYEtXpmWRQ]",
        "envelope": {
            "from": "support@coolsms.zendesk.com",
            "to": [
                "newMail@test.net"
            ]
        },
        "messageId": "<dae09de9-b837-9397-ac49-129a48f1a13a@coolsms.zendesk.com>"
    },
    "invitation": {
        "accountId": "19073041912439",
        "email": "newMail@test.net",
        "dateCreated": "2019-07-30T02:38:36.311Z",
        "dateUpdated": "2019-07-30T02:38:36.311Z",
        "invitationId": "V9adxJfSNO3wPLj3KB7kT",
        "memberId": "MEMdpERE7_U9Qq",
        "role": "DEVELOPER"
    }
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
    email: 'newMail@test.net',
    role: 'DEVELOPER'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/users/v1/invitations'
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
    email: 'newMail@test.net',
    role: 'DEVELOPER'
  },
  method: 'POST',
  url: 'http://api.solapi.com/users/v1/invitations'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/users/v1/invitations";
$data = '{"email":"newMail@test.net","role":"DEVELOPER"}';

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

url = "http://api.solapi.com/users/v1/invitations"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"email":"newMail@test.net","role":"DEVELOPER"}'

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
    -d '{"email":"newMail@test.net","role":"DEVELOPER"}' \
    http://api.solapi.com/users/v1/invitations
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/invitations")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "email": "newMail@test.net",
  "role": "DEVELOPER"
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
  uri := "http://api.solapi.com/users/v1/invitations"
  data := strings.NewReader(`{"email":"newMail@test.net","role":"DEVELOPER"}`)

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
    String targetUrl = "http://api.solapi.com/users/v1/invitations";
    String parameters = "{\"email\":\"newMail@test.net\",\"role\":\"DEVELOPER\"}";

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
