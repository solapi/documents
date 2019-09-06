# 회원 정보 수정

## Request
```
PUT https://api.solapi.com/users/v1/accounts/:accountId/members/:memberId
```

특정 회원의 정보를 해당 회원 혹은 관리자(OWNER)가 수정합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `accounts:write` | `role-accounts:write` | `ACTIVE` | `ACTIVE` | O |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :accountId | 계정 고유 아이디 |
| :memberId | 회원 고유 아이디 |

### Request Structure
```json
{
    "role": "string",
    "name": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| role | `string` |  | 권한 (OWNER, DEVELOPER, MEMBER) |
| name | `string` |  | 이름 |


---

## Samples

### updateAccountMember.spec.js

> **Sample Request**

```json
{
    "name": "Member"
}
```

> **Sample Response**

```json
{
    "dateCreated": "2019-09-06T18:45:50.416Z",
    "dateUpdated": "2019-09-06T18:45:50.439Z",
    "memberId": "18010100001001",
    "role": "MEMBER",
    "name": "Member"
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
    name: 'Member'
  },
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001'
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
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    name: 'Member'
  },
  method: 'PUT',
  url: 'http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001";
$data = '{"name":"Member"}';

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

url = "http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"name":"Member"}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"name":"Member"}' \
	http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "name": "Member"
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
  uri := "http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001"
  data := strings.NewReader(`{"name":"Member"}`)

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
    String targetUrl = "http://api.solapi.com/users/v1/accounts/12925149/members/18010100001001";
    String parameters = "{\"name\":\"Member\"}";

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

---

> 문서 생성일 : 2019-09-06

