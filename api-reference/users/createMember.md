# 초대 수락(비회원)

## Request
```
POST https://api.solapi.com/users/v1/signup/invitations/:invitationId
```

기존에 SOLAPI를 사용하지 않았던 사용자가 초대로 인해 SOLAPI에 가입되고 초대된 계정에 들어가게 됩니다.

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :invitationId | 설명 없음 |

### Request Structure
```json
{
    "password": "string",
    "passwordConfirmation": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| password | `string` | O | 비밀번호 |
| passwordConfirmation | `string` | O | 비밀번호 확인 |


---

## Samples

### createMember.spec.js

> **Sample Request**

```json
{
    "password": "asd123!",
    "passwordConfirmation": "asd123!"
}
```

> **Sample Response**

```json
{
    "status": "ACTIVE",
    "accountId": "19102113788499",
    "name": "test1님의 계정",
    "members": [
        {
            "dateCreated": "2019-10-20T18:49:47.062Z",
            "dateUpdated": "2019-10-20T18:49:47.062Z",
            "memberId": "MEMWppm8z_RI2z",
            "role": "OWNER",
            "name": "test1"
        },
        {
            "dateCreated": "2019-10-20T18:49:47.062Z",
            "dateUpdated": "2019-10-20T18:49:47.062Z",
            "memberId": "MEMMoY19Zp5TEM",
            "name": "newMember",
            "role": "DEVELOPER"
        }
    ],
    "dateCreated": "2019-10-20T18:49:48.891Z",
    "dateUpdated": "2019-10-20T18:49:48.906Z"
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    'Content-Type': 'application/json'
  },
  body: {
    password: 'asd123!',
    passwordConfirmation: 'asd123!'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm'
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
    'Content-Type': 'application/json'
  },
  body: {
    password: 'asd123!',
    passwordConfirmation: 'asd123!'
  },
  method: 'POST',
  url: 'http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm";
$data = '{"password":"asd123!","passwordConfirmation":"asd123!"}';

$options = array(
    'http' => array(
        'header'  => "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm"
headers = {
  "Content-Type": "application/json"
}
data = '{"password":"asd123!","passwordConfirmation":"asd123!"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Content-Type: application/json' \
	-d '{"password":"asd123!","passwordConfirmation":"asd123!"}' \
	http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm")

headers = {
  "Content-Type": "application/json"
}
data = {
  "password": "asd123!",
  "passwordConfirmation": "asd123!"
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
  uri := "http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm"
  data := strings.NewReader(`{"password":"asd123!","passwordConfirmation":"asd123!"}`)

  req, err := http.NewRequest("POST", uri, data)
  if err != nil { panic(err) }

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
    String targetUrl = "http://api.solapi.com/users/v1/signup/invitations/CTbhz0F_j9_OWAVcrA3Gm";
    String parameters = "{\"password\":\"asd123!\",\"passwordConfirmation\":\"asd123!\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

> 문서 생성일 : 2019-10-20

