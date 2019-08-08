# 템플릿 검수 요청

## Request

```text
PUT https://api.solapi.com/kakao/v1/templates/:templateId/inspection
```

템플릿을 검수 요청합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` |  | O |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :templateId | 템플릿 고유 아이디 |

## Samples

### REJECTED 상태 검수 요청

> **Sample Request**

```text
{}
```

> **Sample Response**

```javascript
{
    "status": "INSPECTING",
    "accountId": "12925149",
    "templateId": "KA01TP190726074552183JNfSmggywcp",
    "name": "A2",
    "pfId": "PF01ID190726074551033K7cibxpXdQI",
    "content": "testMessage",
    "dateCreated": "2019-07-26T06:45:52.183Z",
    "dateUpdated": "2019-07-26T06:45:52.207Z",
    "buttons": [],
    "comments": []
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
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection'
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
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection";

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

url = "http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection"
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
    http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection")

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
  uri := "http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/KA01TP190726074552183JNfSmggywcp/inspection";

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
