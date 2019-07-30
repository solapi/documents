# 내 초대 조회

#### Request
```
GET https://api.solapi.com/users/v1/invitations
```

내가 받은 초대 목록을 조회합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `users:read` |  |  | `ACTIVE` `UNVERIFIED` |  |

---

#### Samples

##### 정상

> **Sample Request**

```
{}
```

> **Sample Response**

```json
[
    {
        "email": "testOrigin@test.net",
        "invitationId": "iqPkNRHy4atyQeepjeXDO",
        "role": "MEMBER",
        "dateCreated": "2019-07-30T02:38:40.552Z",
        "dateUpdated": "2019-07-30T02:38:40.552Z",
        "owner": {
            "name": "test1",
            "phoneNumber": null,
            "status": "UNVERIFIED",
            "selectedAccountId": "19073041920411",
            "isAdmin": false,
            "memberId": "MEMrAaBs6_HCLT",
            "email": "test1@test.com",
            "loginSessions": [],
            "dateCreated": "2019-07-30T02:38:40.543Z",
            "dateUpdated": "2019-07-30T02:38:40.545Z"
        },
        "account": {
            "status": "ACTIVE",
            "accountId": "19073041920411",
            "name": "test1님의 계정",
            "dateCreated": "2019-07-30T02:38:40.547Z",
            "dateUpdated": "2019-07-30T02:38:40.547Z"
        }
    },
    {
        "email": "testOrigin@test.net",
        "invitationId": "UVyI3y01aLn_VU9FFSNEp",
        "role": "DEVELOPER",
        "dateCreated": "2019-07-30T02:38:40.554Z",
        "dateUpdated": "2019-07-30T02:38:40.554Z",
        "owner": {
            "name": "test2",
            "phoneNumber": null,
            "status": "UNVERIFIED",
            "selectedAccountId": "19073041920142",
            "isAdmin": false,
            "memberId": "MEMItbE5h9vJO4",
            "email": "test2@test.com",
            "loginSessions": [],
            "dateCreated": "2019-07-30T02:38:40.544Z",
            "dateUpdated": "2019-07-30T02:38:40.549Z"
        },
        "account": {
            "status": "ACTIVE",
            "accountId": "19073041920142",
            "name": "test2님의 계정",
            "dateCreated": "2019-07-30T02:38:40.550Z",
            "dateUpdated": "2019-07-30T02:38:40.550Z"
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
    Authorization: 'Bearer eyJhbGciOiJI...'
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

{% tab title="JQUERY" %}

```javascript
var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  url: 'http://api.solapi.com/users/v1/invitations'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/users/v1/invitations";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
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
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
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
  "Authorization": "Bearer eyJhbGciOiJI..."
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
    String targetUrl = "http://api.solapi.com/users/v1/invitations";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

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

---

