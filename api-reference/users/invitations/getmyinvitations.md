# 내 초대 조회

## Request

```text
GET https://api.solapi.com/users/v1/invitations
```

내가 받은 초대 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `users:read` |  |  | `ACTIVE` `UNVERIFIED` |  |

## Samples

### getMyInvitations.spec.js

> **Sample Request**

```text
http://api.solapi.com/users/v1/invitations
```

> **Sample Response**

```javascript
[
    {
        "email": "testOrigin@test.net",
        "invitationId": "iqPkNRHy4atyQeepjeXDO",
        "role": "MEMBER",
        "dateCreated": "2020-09-23T03:40:16.867Z",
        "dateUpdated": "2020-09-23T03:40:16.867Z",
        "owner": {
            "name": "test1",
            "phoneNumber": null,
            "extraPhoneNumbers": [],
            "status": "UNVERIFIED",
            "selectedAccountId": "20092345616839",
            "isAdmin": false,
            "betaMicroservices": null,
            "appId": null,
            "memberId": "MEMISfoLP2Ubqu",
            "email": "test1@test.com",
            "loginSessions": [],
            "dateCreated": "2020-09-23T03:40:16.852Z",
            "dateUpdated": "2020-09-23T03:40:16.855Z"
        },
        "account": {
            "status": "ACTIVE",
            "accountId": "20092345616839",
            "name": "test1님의 계정",
            "dateCreated": "2020-09-23T03:40:16.858Z",
            "dateUpdated": "2020-09-23T03:40:16.858Z"
        }
    },
    {
        "email": "testOrigin@test.net",
        "invitationId": "UVyI3y01aLn_VU9FFSNEp",
        "role": "DEVELOPER",
        "dateCreated": "2020-09-23T03:40:16.868Z",
        "dateUpdated": "2020-09-23T03:40:16.868Z",
        "owner": {
            "name": "test2",
            "phoneNumber": null,
            "extraPhoneNumbers": [],
            "status": "UNVERIFIED",
            "selectedAccountId": "20092345616626",
            "isAdmin": false,
            "betaMicroservices": null,
            "appId": null,
            "memberId": "MEMzXjm9j2SdCU",
            "email": "test2@test.com",
            "loginSessions": [],
            "dateCreated": "2020-09-23T03:40:16.853Z",
            "dateUpdated": "2020-09-23T03:40:16.861Z"
        },
        "account": {
            "status": "ACTIVE",
            "accountId": "20092345616626",
            "name": "test2님의 계정",
            "dateCreated": "2020-09-23T03:40:16.863Z",
            "dateUpdated": "2020-09-23T03:40:16.863Z"
        }
    }
]
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/users/v1/invitations'
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
$url = "http://api.solapi.com/users/v1/invitations";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'GET'
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

url = "http://api.solapi.com/users/v1/invitations"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X GET \
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
    http://api.solapi.com/users/v1/invitations
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/invitations")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, headers)

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
  uri := "http://api.solapi.com/users/v1/invitations"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")

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
    String targetUrl = "http://api.solapi.com/users/v1/invitations";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");

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

