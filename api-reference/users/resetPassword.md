# 비밀번호 초기화

## Request
```
PUT https://api.solapi.com/users/v1/member/password/reset/:hashId
```

비밀번호를 초기화합니다.

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :hashId | 설명 없음 |

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

### resetPassword.spec.js

> **Sample Request**

```json
{
    "password": "asd456!",
    "passwordConfirmation": "asd456!"
}
```

> **Sample Response**

```json
{
    "name": "steven",
    "phoneNumber": null,
    "status": "UNVERIFIED",
    "selectedAccountId": null,
    "memberId": "MEMag_UIQroNOD",
    "email": "steven@nurigo.net",
    "loginSessions": [],
    "dateCreated": "2019-11-02T16:14:16.820Z",
    "dateUpdated": "2019-11-02T16:14:16.828Z"
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
    password: 'asd456!',
    passwordConfirmation: 'asd456!'
  },
  method: 'PUT',
  json: true,
  url:
    'http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl'
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
    password: 'asd456!',
    passwordConfirmation: 'asd456!'
  },
  method: 'PUT',
  url:
    'http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl";
$data = '{"password":"asd456!","passwordConfirmation":"asd456!"}';

$options = array(
    'http' => array(
        'header'  => "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl"
headers = {
  "Content-Type": "application/json"
}
data = '{"password":"asd456!","passwordConfirmation":"asd456!"}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Content-Type: application/json' \
	-d '{"password":"asd456!","passwordConfirmation":"asd456!"}' \
	http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl")

headers = {
  "Content-Type": "application/json"
}
data = {
  "password": "asd456!",
  "passwordConfirmation": "asd456!"
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
  uri := "http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl"
  data := strings.NewReader(`{"password":"asd456!","passwordConfirmation":"asd456!"}`)

  req, err := http.NewRequest("PUT", uri, data)
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
    String targetUrl = "http://api.solapi.com/users/v1/member/password/reset/W4MPzsVpGy9KBOjvF1xRl";
    String parameters = "{\"password\":\"asd456!\",\"passwordConfirmation\":\"asd456!\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

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

> 문서 생성일 : 2019-11-02

