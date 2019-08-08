# 이미지 생성

## Request

```text
POST https://api.solapi.com/images/v4/images
```

계정에 이미지를 생성합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `images:write` | `role-images:write` | `ACTIVE` |  |  |

### Request Structure

```javascript
{
    "image": "binary"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| image | `binary` | O | 이미지가 인코딩 된 형태의 문자열 |

## Samples

### createImages handler 가 정상작동하는가?

> **Sample Request**

```javascript
{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAPcAAAD3CAYAAADBjMJTAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAA+ZpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMC1jMDYwIDYxLjEzNDc3NywgMjAxMC8wMi8xMi0xNzozMjowMCAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wTU09Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9tbS8iIHhtbG5zOnN0UmVmPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvc1R5cGUvUmVzb3VyY2VSZWYjIiB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iIHhtbG5zOmRjPSJodHRwOi8vcHVybC5vcmcvZGMvZWxlbWVudHMvMS4xLyIgeG1wTU06T3JpZ2luYWxEb2N1bWVudElEPSJ1dWlkOjY1RTYzOTA2ODZDRjExREJBNkUyRDg4N0NFQUNCNDA3IiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOjVDMTMxM0Q2NTJENzExRTVCMzU2ODAwMTc4Njg0OTJFIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOjVDMTMxM0Q1NTJENzExRTVCMzU2ODAwMTc4Njg0OTJFIiB4bXA6Q3JlYXRvclRvb2w9IkFkb2JlIElsbHVzdHJhdG9yIENTNSI+IDx4bXBNTTpEZXJpdmVkRnJvbSBzdFJlZjppbnN0YW5jZUlEPSJ1dWlkOjBiZmNiMzczLTViYjYtNDVhNC04NTA5LWZjMzE0ZTQ1YTkyYSIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo4OUNBRThGNkI5MzJFMjEx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"
}
```

> **Sample Response**

```javascript
{
    "imageId": "M4V201907261540405GSLD6TGYY9XOBO"
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAPc...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/images/v4/images'
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAPc...'
  },
  method: 'POST',
  url: 'http://api.solapi.com/images/v4/images'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/images/v4/images";
$data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAPc..."}';

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

url = "http://api.solapi.com/images/v4/images"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAPc..."}'

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
    -d '{"image":"iVBORw0KGgoAAAANSUhEUgAAAPc..."}' \
    http://api.solapi.com/images/v4/images
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/images/v4/images")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "image": "iVBORw0KGgoAAAANSUhEUgAAAPc..."
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
  uri := "http://api.solapi.com/images/v4/images"
  data := strings.NewReader(`{"image":"iVBORw0KGgoAAAANSUhEUgAAAPc..."}`)

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
    String targetUrl = "http://api.solapi.com/images/v4/images";
    String parameters = "{\"image\":\"iVBORw0KGgoAAAANSUhEUgAAAPc...\"}";

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

