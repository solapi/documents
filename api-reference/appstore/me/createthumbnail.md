# 썸네일 업로드

## Request

```text
POST https://api.solapi.com/appstore/v2/me/apps/:appId/images/thumbnail
```

200x200 사이즈의 PNG, JPG, GIF 포맷의 썸네일 이미지 업로드

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `appstore:write` | `role-appstore:write` | `ACTIVE` | `ACTIVE` | O |

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

### \(User\) 썸네일 이미지 업로드

> **Sample Request**

```javascript
{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAMg..."
}
```

> **Sample Response**

```javascript
{
    "appId": "QKhNm6t6oQmO",
    "imageName": "xFzgeV1Py2fEJmh.png",
    "imageUrl": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/QKhNm6t6oQmO/thumbnails/xFzgeV1Py2fEJmh.png",
    "originalName": "xFzgeV1Py2fEJmh.png"
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAMg...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail";
$data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
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
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    -H 'Content-Type: application/json' \
    -d '{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}' \
    http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
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
  uri := "http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail"
  data := strings.NewReader(`{"image":"iVBORw0KGgoAAAANSUhEUgAAAMg..."}`)

  req, err := http.NewRequest("POST", uri, data)
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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps/QKhNm6t6oQmO/images/thumbnail";
    String parameters = "{\"image\":\"iVBORw0KGgoAAAANSUhEUgAAAMg...\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

> 문서 생성일 : 2020-09-23

