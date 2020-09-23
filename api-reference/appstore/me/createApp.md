# 앱 생성

## Request
```
POST https://api.solapi.com/appstore/v2/me/apps
```

자신의 앱을 생성합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `appstore:write` | `role-appstore:write` | `ACTIVE` | `ACTIVE` | O |

### Request Structure
```json
{
    "appName": "string",
    "appVersion": "string",
    "thumbnail": "string",
    "screenshots": "array",
    "homepage": "string",
    "profit": "object",
    "categories": "array",
    "intro": "string",
    "description": "string",
    "email": "email",
    "type": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| appName | `string` | O | 앱 이름 |
| appVersion | `string` |  | 앱 버전 |
| thumbnail | `string` |  | 미리보기 사진 (썸네일) |
| screenshots | `array` |  | 컨텐츠 이미지 |
| homepage | `string` |  | 홈페이지 주소(링크) |
| [profit](#body-profit) | `object` |  | 수익 |
| categories | `array` |  | 카테고리 |
| intro | `string` |  | 앱 소개 |
| description | `string` |  | 앱 설명 |
| email | `email` |  | 이메일 |
| type | `string` |  | 설명 없음 |


##### Body / profit

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| sms | `number` | O | 단문 메시지 |
| lms | `number` | O | 장문 메시지 |
| mms | `number` | O | 이미지 + 장문 메시지 |
| ata | `number` | O | 알림톡 |
| cta | `number` | O | 친구톡 |
| cti | `number` | O | 친구톡 이미지 |



---

## Samples

### (User) 앱 생성

> **Sample Request**

```json
{
    "appName": "App Name"
}
```

> **Sample Response**

```json
{
    "clientSecret": "ZHEACK3CQSQD1KEQLIESNO4T2COFIWBW",
    "thumbnail": {
        "name": null,
        "url": null,
        "originalName": null
    },
    "profit": {
        "sms": 0,
        "lms": 0,
        "mms": 0,
        "ata": 0,
        "cta": 0,
        "cti": 0
    },
    "apphomeConfig": {
        "primaryColor": null,
        "secondaryColor": null,
        "sideMenu": true,
        "slogan": true
    },
    "appVersion": null,
    "screenshots": [],
    "homepage": null,
    "categories": [],
    "intro": null,
    "description": null,
    "stage": "DEVELOP",
    "status": "ACTIVE",
    "reasonBlocked": null,
    "email": null,
    "log": [],
    "appDomain": null,
    "customDomain": null,
    "type": "APP",
    "accountId": "12925149",
    "clientId": "CIDCRXFULDIG2YRZ",
    "appName": "App Name",
    "appId": "XqANobnyOkvm",
    "dateCreated": "2020-09-23T02:34:51.079Z",
    "dateUpdated": "2020-09-23T02:34:51.079Z"
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
    appName: 'App Name'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/me/apps'
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
$url = "http://api.solapi.com/appstore/v2/me/apps";
$data = '{"appName":"App Name"}';

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

url = "http://api.solapi.com/appstore/v2/me/apps"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"appName":"App Name"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"appName":"App Name"}' \
	http://api.solapi.com/appstore/v2/me/apps
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "appName": "App Name"
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
  uri := "http://api.solapi.com/appstore/v2/me/apps"
  data := strings.NewReader(`{"appName":"App Name"}`)

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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps";
    String parameters = "{\"appName\":\"App Name\"}";

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

---

> 문서 생성일 : 2020-09-23

