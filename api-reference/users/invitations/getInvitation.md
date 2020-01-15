# 초대 조회

## Request
```
GET https://api.solapi.com/users/v1/invitations/:invitationId
```

초대장 정보를 조회합니다.

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :invitationId | 설명 없음 |

---

## Samples

### getInvitation.spec.js

> **Sample Request**

```
http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe
```

> **Sample Response**

```json
{
    "invitationId": "BoMnjbF4JMaoeRlWX3fDe",
    "role": "DEVELOPER",
    "email": "test33@nurigo.net",
    "dateCreated": "2019-12-30T21:54:38.065Z",
    "dateUpdated": "2019-12-30T21:54:38.065Z",
    "account": {
        "status": "ACTIVE",
        "accountId": "19123124878206",
        "name": "test님의 계정",
        "dateCreated": "2019-12-30T21:54:38.055Z",
        "dateUpdated": "2019-12-30T21:54:38.055Z"
    },
    "owner": {
        "name": "test",
        "phoneNumber": null,
        "status": "UNVERIFIED",
        "selectedAccountId": "19123124878206",
        "memberId": "MEMr0pdGIA1mea",
        "email": "test@nurigo.net",
        "loginSessions": [],
        "dateCreated": "2019-12-30T21:54:38.050Z",
        "dateUpdated": "2019-12-30T21:54:38.052Z"
    }
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe'
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
$url = "http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe";

$options = array(
    'http' => array(
        'header'  => ,
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

url = "http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe"

response = requests.get(url)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe")

http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, )

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
  uri := "http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

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
    String targetUrl = "http://api.solapi.com/users/v1/invitations/BoMnjbF4JMaoeRlWX3fDe";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");


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

> 문서 생성일 : 2019-12-30
