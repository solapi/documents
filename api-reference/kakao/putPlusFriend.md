# 카카오톡채널 추가

## Request
```
POST https://api.solapi.com/kakao/v1/plus-friends/:service
```

기존에 등록된 카카오톡채널을 SOLAPI에 연동합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:write` | `role-kakao:write` | `ACTIVE` | `ACTIVE` | O |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :service | 카카오톡채널 연동처 |

### Request Structure
```json
{
    "searchId": "string",
    "phoneNumber": "string",
    "categoryCode": "string",
    "token": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| searchId | `string` | O | 카카오톡채널 검색용 아이디 |
| phoneNumber | `string` | O | 핸드폰 번호 |
| categoryCode | `string` | O | 카카오톡채널 카테고리 코드 |
| token | `string` | O | 연동 시 카카오톡으로 사용자에게 오는 토큰 |


---

## Samples

### putPlusFriend.spec.js

> **Sample Request**

```json
{
    "searchId": "NURIGO",
    "phoneNumber": "01055555555",
    "categoryCode": "02536589547",
    "token": "123456789"
}
```

> **Sample Response**

```json
{
    "accountId": "19301859371938",
    "phoneNumber": "01055555555",
    "searchId": "NURIGO",
    "dateCreated": "2019-12-17T22:29:36.246Z",
    "dateUpdated": "2019-12-17T22:29:36.246Z",
    "pfId": "KA01PF191217222936250AUOMQeD9edz",
    "senderKeys": [
        {
            "service": "daou",
            "key": "11646846a8ds4f6a84fs6a8sf4",
            "categoryCode": "02536589547"
        }
    ]
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
    searchId: 'NURIGO',
    phoneNumber: '01055555555',
    categoryCode: '02536589547',
    token: '123456789'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/kakao/v1/plus-friends/daou'
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
$url = "http://api.solapi.com/kakao/v1/plus-friends/daou";
$data = '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}';

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

url = "http://api.solapi.com/kakao/v1/plus-friends/daou"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}'

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
	-d '{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}' \
	http://api.solapi.com/kakao/v1/plus-friends/daou
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/plus-friends/daou")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "searchId": "NURIGO",
  "phoneNumber": "01055555555",
  "categoryCode": "02536589547",
  "token": "123456789"
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
  uri := "http://api.solapi.com/kakao/v1/plus-friends/daou"
  data := strings.NewReader(`{"searchId":"NURIGO","phoneNumber":"01055555555","categoryCode":"02536589547","token":"123456789"}`)

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
    String targetUrl = "http://api.solapi.com/kakao/v1/plus-friends/daou";
    String parameters = "{\"searchId\":\"NURIGO\",\"phoneNumber\":\"01055555555\",\"categoryCode\":\"02536589547\",\"token\":\"123456789\"}";

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

> 문서 생성일 : 2019-12-17

