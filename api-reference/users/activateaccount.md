# 휴면 계정 활성화

## Request

```text
PUT https://api.solapi.com/users/v1/accounts/:accountId/activate
```

휴면 처리된 계정을 활성화합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `accounts:write` | `role-accounts:write` | `INACTIVE` | `ACTIVE` |  |

### 2차 인증 필요

| ARS 전화 인증 | 이메일 OTP |
| :---: | :---: |
|  |  |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :accountId | 계정 고유 아이디 |

## Samples

### 어카운트가 INACTIVE 상태일때 ACTIVATE 요청

> **Sample Request**

```text
{}
```

> **Sample Response**

```javascript
{
    "status": "ACTIVE",
    "accountId": "214727",
    "name": "누리테스트2",
    "members": [
        {
            "dateCreated": "2019-07-30T02:38:40.273Z",
            "dateUpdated": "2019-07-30T02:38:40.273Z",
            "memberId": "18010100001000",
            "role": "OWNER",
            "name": "toss 0"
        },
        {
            "dateCreated": "2019-07-30T02:38:40.273Z",
            "dateUpdated": "2019-07-30T02:38:40.273Z",
            "memberId": "18010100001001",
            "role": "MEMBER",
            "name": "toss 1"
        }
    ],
    "dateCreated": "2019-07-30T02:38:40.276Z",
    "dateUpdated": "2019-07-30T02:38:40.298Z"
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
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/users/v1/accounts/214727/activate'
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
  method: 'PUT',
  url: 'http://api.solapi.com/users/v1/accounts/214727/activate'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/users/v1/accounts/214727/activate";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
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

url = "http://api.solapi.com/users/v1/accounts/214727/activate"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.put(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X PUT \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    http://api.solapi.com/users/v1/accounts/214727/activate
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/accounts/214727/activate")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
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
  uri := "http://api.solapi.com/users/v1/accounts/214727/activate"

  req, err := http.NewRequest("PUT", uri, nil)
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
    String targetUrl = "http://api.solapi.com/users/v1/accounts/214727/activate";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

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

