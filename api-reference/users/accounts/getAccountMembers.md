# 계정 회원 목록 조회

## Request
```
GET https://api.solapi.com/users/v1/accounts/:accountId/members
```

회원 혹은 관리자(OWNER)가 자신이 속해있는 계정의 맴버 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `accounts:read` | `role-accounts:read` | `ACTIVE` | `ACTIVE` `UNVERIFIED` |  |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :accountId | 계정 고유 아이디 |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| memberId | `string` |  | eq | 회원 고유 아이디 |
| role | `string` |  | eq | 권한 (OWNER, DEVELOPER, MEMBER) |
| name | `string` |  | eq | 이름 |
| email | `email` |  | eq | 이메일 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| status | `string` |  | eq | 상태값 |
| dateCreated | `date` |  | eq | 최초 생성 날짜 |

---

## Samples

### getAccountMembers.spec.js

> **Sample Request**

```
http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003
```

> **Sample Response**

```json
{
    "data": [
        {
            "memberId": "18010100001003",
            "role": "MEMBER",
            "name": "testName 3",
            "email": "test3@nurigo.net",
            "status": "ACTIVE",
            "dateCreated": "2020-09-23T03:40:14.725Z",
            "dateUpdated": "2020-09-23T03:40:14.725Z"
        },
        {
            "memberId": "18010100001002",
            "role": "MEMBER",
            "name": "testName 2",
            "email": "test2@nurigo.net",
            "status": "ACTIVE",
            "dateCreated": "2020-09-23T03:40:14.725Z",
            "dateUpdated": "2020-09-23T03:40:14.725Z"
        },
        {
            "memberId": "18010100001001",
            "role": "MEMBER",
            "name": "testName 1",
            "email": "test1@nurigo.net",
            "status": "ACTIVE",
            "dateCreated": "2020-09-23T03:40:14.725Z",
            "dateUpdated": "2020-09-23T03:40:14.725Z"
        },
        {
            "memberId": "18010100001000",
            "role": "OWNER",
            "name": "testName 0",
            "email": "test0@nurigo.net",
            "status": "ACTIVE",
            "dateCreated": "2020-09-23T03:40:14.725Z",
            "dateUpdated": "2020-09-23T03:40:14.725Z"
        }
    ],
    "nextKey": null
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url:
    'http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003'
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
$url = "http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003";

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

url = "http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
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
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003")

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
  uri := "http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003"

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
    String targetUrl = "http://api.solapi.com/users/v1/accounts/12925149/members?startKey=18010100001003";

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

---

> 문서 생성일 : 2020-09-23

