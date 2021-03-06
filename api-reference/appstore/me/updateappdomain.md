# 앱에 앱홈 도메인 업데이트

## Request

```text
PUT https://api.solapi.com/appstore/v2/me/apps/:appId/apphome
```

앱홈 서비스를 이용하기 위한 도메인을 변경합니다.

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
    "domainPrefix": "string",
    "customDomain": "string",
    "primaryColor": "string",
    "secondaryColor": "string",
    "sideMenu": "boolean",
    "slogan": "boolean"
}
```

### Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| domainPrefix | `string` |  | 설명 없음 |
| customDomain | `string` |  | 설명 없음 |
| primaryColor | `string` |  | 설명 없음 |
| secondaryColor | `string` |  | 설명 없음 |
| sideMenu | `boolean` |  | 설명 없음 |
| slogan | `boolean` |  | 설명 없음 |

## Samples

### 앱홈 도메인 업데이트

> **Sample Request**

```javascript
{
    "domainPrefix": "4989",
    "primaryColor": "#fff",
    "slogan": false
}
```

> **Sample Response**

```javascript
{
    "_id": "5f6ab44eb992b12976c9c183",
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
        "primaryColor": "#fff",
        "secondaryColor": null,
        "sideMenu": true,
        "slogan": false
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
    "appDomain": "4989.solapi.net",
    "customDomain": null,
    "type": "SITE",
    "accountId": "12925149",
    "appName": "A-APP",
    "appId": "ACMn6vXrElA",
    "clientId": "CIDL39VZZN8HO8UA",
    "dateCreated": "2020-09-23T02:34:54.140Z",
    "dateUpdated": "2020-09-23T02:34:54.149Z",
    "CNAME": "hosting.solapi.net"
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
    domainPrefix: '4989',
    primaryColor: '#fff',
    slogan: false
  },
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome'
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
$url = "http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome";
$data = '{"domainPrefix":"4989","primaryColor":"#fff","slogan":false}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"domainPrefix":"4989","primaryColor":"#fff","slogan":false}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X PUT \
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    -H 'Content-Type: application/json' \
    -d '{"domainPrefix":"4989","primaryColor":"#fff","slogan":false}' \
    http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "domainPrefix": "4989",
  "primaryColor": "#fff",
  "slogan": false
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
  uri := "http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome"
  data := strings.NewReader(`{"domainPrefix":"4989","primaryColor":"#fff","slogan":false}`)

  req, err := http.NewRequest("PUT", uri, data)
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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps/ACMn6vXrElA/apphome";
    String parameters = "{\"domainPrefix\":\"4989\",\"primaryColor\":\"#fff\",\"slogan\":false}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

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

