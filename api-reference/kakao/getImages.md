# 친구톡 이미지 목록 조회

#### Request
```
GET https://api.solapi.com/kakao/v1/images
```

친구톡 이미지 목록을 조회합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:read` | `role-kakao:read` |  |  |  |

##### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| imageId | `string` |  | eq | 이미지 아이디 |
| imageUrl | `string` |  | eq | 이미지 주소 |
| title | `string` |  | eq, ne, like | 제목 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateCreated | `date` |  | eq, gte, lte, gt, lt | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq, gte, lte, gt, lt | 최초 생성 날짜 |

---

#### Samples

##### 이미지 업로드

> **Sample Request**

```
{}
```

> **Sample Response**

```json
{
    "imageId": "KA01IM190726074551409BMHCrhn0cFs",
    "accountId": "19020720648888",
    "title": "012345678901234567890123456789012345678901234567890123456789",
    "link": "012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234",
    "imageUrl": "http://mud-kage.kakao.com/dn/gtM0a/btqtfj5pQ92/meXjtBKhjbdKSh2aK8Wu3k/img_l.png",
    "dateCreated": "2019-07-26T06:45:51.411Z",
    "dateUpdated": "2019-07-26T06:45:51.411Z"
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAyA...',
    title: '012345678901234567890123456...',
    link: '012345678901234567890123456...'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/kakao/v1/images'
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
    image: 'iVBORw0KGgoAAAANSUhEUgAAAyA...',
    title: '012345678901234567890123456...',
    link: '012345678901234567890123456...'
  },
  method: 'POST',
  url: 'http://api.solapi.com/kakao/v1/images'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/kakao/v1/images";
$data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA...","title":"012345678901234567890123456...","link":"012345678901234567890123456..."}';

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

url = "http://api.solapi.com/kakao/v1/images"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA...","title":"012345678901234567890123456...","link":"012345678901234567890123456..."}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-H 'Content-Type: application/json' \
	-d '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA...","title":"012345678901234567890123456...","link":"012345678901234567890123456..."}' \
	http://api.solapi.com/kakao/v1/images
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/images")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "image": "iVBORw0KGgoAAAANSUhEUgAAAyA...",
  "title": "012345678901234567890123456...",
  "link": "012345678901234567890123456..."
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
  uri := "http://api.solapi.com/kakao/v1/images"
  data := strings.NewReader(`{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA...","title":"012345678901234567890123456...","link":"012345678901234567890123456..."}`)

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
    String targetUrl = "http://api.solapi.com/kakao/v1/images";
    String parameters = "{\"image\":\"iVBORw0KGgoAAAANSUhEUgAAAyA...\",\"title\":\"012345678901234567890123456...\",\"link\":\"012345678901234567890123456...\"}";

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

---

