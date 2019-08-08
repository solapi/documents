# 썸네일 업로드

## Request

```text
POST https://api.solapi.com/appstore/v2/me/apps/:appId/images/thumbnail
```

200x200 사이즈의 PNG, JPG, GIF 포맷의 썸네일 이미지 업로드

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `appstore:write` | `role-appstore:write` | `ACTIVE` |  | O |

### Path Parameters

| Name | Description |
| :---: | :---: |
| :appId | 앱 아이디 |

### Request Structure

```javascript
{
    "image": "string",
    "name": "string"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| image | `string` | O | 800x600 사이즈의 PNG, JPG, GIF 포맷의 컨텐츠 이미지 |
| name | `string` |  | 사진 이름 |

## Samples

### \(성공\) 200x200 PNG 업로드

> **Sample Request**

```javascript
{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAMgAAADIBAMAAABfdrOtAAAAG1BMVEU/j2////9vq5PP49vn8e2fx7e31clXnYGHuaX7Q2KjAAAACXBIWXMAAA7EAAAOxAGVKw4bAAABrklEQVR4nO3UT0/CMBjH8ccx2I56IF6nkHglQoxHnX/gSKIvwBi9TyWel7gX7tP2GQpEE4revp+EluX3ZN3ariIAAAAAAAAAAAAAAAAA8JvjwrXZsb94Ldbj5HtgVdtKJuPLuXbX4xu9Gl5N5qv54GrSXwZWtbVeIdmt3qSQtwdJSsnOVvNHkcUyCFVxjiqZaTeTtBb/W5UctkGoipMW+YV2H9Jom4828tICq4rTqXtuJV7kWdtsX5tuoc17m59bYFVx9qpOrV1anburqf50DSRbTsyhhMCq4gZpdMK06xSluzp1jS7xorZYZykEVhU3yCw8Xqd2LxGeOp9+vUhaSwisKmqM7mhzEGma5c3u5A8GaarN6ZJuv43zqew+XcnUHu/bwusX+NQu8LCS3Rde11jWt7Burby0Z3D9rls491v2QtxnNpT2Y9St1RQ+b9yTh8CqItz713dbqZS0lrA8bmv5V5Cunz0LQtX2emEJhrU/IGd2QPb0pjJw/8LSWBCqtnd0oObuxHeH+GD9qE9c3G8Dq4qWnfju9ae9EwKrAgAAAAAAAAAAAAAAAPAfPgFZpkiD9I8rfAAAAABJRU5ErkJggg=="
}
```

> **Sample Response**

```javascript
{
    "appId": "4icxMtJwxUAQ",
    "imageName": "BvWxdBovuMfcuuE.png",
    "imageUrl": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/4icxMtJwxUAQ/thumbnails/BvWxdBovuMfcuuE.png",
    "originalName": "BvWxdBovuMfcuuE.png"
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAMg...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail'
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAMg...'
  },
  method: 'POST',
  url: 'http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail";
$data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}';

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

url = "http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}'

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
    -d '{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}' \
    http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "image": "iVBORw0KGgoAAAANSUhEUgAAAMg..."
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
  uri := "http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail"
  data := strings.NewReader(`{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}`)

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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps/4icxMtJwxUAQ/images/thumbnail";
    String parameters = "{\"image\":\"iVBORw0KGgoAAAANSUhEUgAAAMg...\"}";

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

