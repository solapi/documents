# 사업자 정보 등록

## Request
```
POST https://api.solapi.com/cash/v1/company
```

사업자 정보를 등록합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `cash:write` | `role-cash:write` | `ACTIVE` | `ACTIVE` | O |

### Request Structure
```json
{
    "name": "string",
    "owner": "string",
    "address": "string",
    "businessNumber": "string",
    "businessType": "string",
    "businessItems": "string",
    "contacts": "array"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| name | `string` | O | 회사명 |
| owner | `string` | O | 대표자 |
| address | `string` | O | 사업장 주소  |
| businessNumber | `string` | O | 사업자 번호 |
| businessType | `string` | O | 사업자 형태 (개인 | 법인) |
| businessItems | `string` | O | 업종 (업태 + 종목) |
| [contacts](#body-contacts) | `array` | O | 담당자 |


##### Body / contacts

| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| name | `string` |  | 회사명 |
| email | `email` |  | 이메일 |
| phone | `string` |  | 연락처 |


---

## Samples

### createCompany.spec.js

> **Sample Request**

```json
{
    "name": "회사이름",
    "owner": "대표자이름",
    "address": "회사주소",
    "businessNumber": "사업자정보",
    "businessType": "업태",
    "businessItems": "종목",
    "contacts": [
        {
            "name": "contact name",
            "email": "contact@email.com",
            "phone": "contact phone"
        }
    ]
}
```

> **Sample Response**

```json
{
    "companyId": "10627101742927858001569566270373"
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
    name: '회사이름',
    owner: '대표자이름',
    address: '회사주소',
    businessNumber: '사업자정보',
    businessType: '업태',
    businessItems: '종목',
    contacts: [
      {
        name: 'contact name',
        email: 'contact@email.com',
        phone: 'contact phone'
      }
    ]
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/cash/v1/company'
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
    name: '회사이름',
    owner: '대표자이름',
    address: '회사주소',
    businessNumber: '사업자정보',
    businessType: '업태',
    businessItems: '종목',
    contacts: [
      {
        name: 'contact name',
        email: 'contact@email.com',
        phone: 'contact phone'
      }
    ]
  },
  method: 'POST',
  url: 'http://api.solapi.com/cash/v1/company'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/cash/v1/company";
$data = '{"name":"회사이름","owner":"대표자이름","address":"회사주소","businessNumber":"사업자정보","businessType":"업태","businessItems":"종목","contacts":[{"name":"contact name","email":"contact@email.com","phone":"contact phone"}]}';

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

url = "http://api.solapi.com/cash/v1/company"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"name":"회사이름","owner":"대표자이름","address":"회사주소","businessNumber":"사업자정보","businessType":"업태","businessItems":"종목","contacts":[{"name":"contact name","email":"contact@email.com","phone":"contact phone"}]}'

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
	-d '{"name":"회사이름","owner":"대표자이름","address":"회사주소","businessNumber":"사업자정보","businessType":"업태","businessItems":"종목","contacts":[{"name":"contact name","email":"contact@email.com","phone":"contact phone"}]}' \
	http://api.solapi.com/cash/v1/company
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/company")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "name": "회사이름",
  "owner": "대표자이름",
  "address": "회사주소",
  "businessNumber": "사업자정보",
  "businessType": "업태",
  "businessItems": "종목",
  "contacts": [
    {
      "name": "contact name",
      "email": "contact@email.com",
      "phone": "contact phone"
    }
  ]
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
  uri := "http://api.solapi.com/cash/v1/company"
  data := strings.NewReader(`{"name":"회사이름","owner":"대표자이름","address":"회사주소","businessNumber":"사업자정보","businessType":"업태","businessItems":"종목","contacts":[{"name":"contact name","email":"contact@email.com","phone":"contact phone"}]}`)

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
    String targetUrl = "http://api.solapi.com/cash/v1/company";
    String parameters = "{\"name\":\"회사이름\",\"owner\":\"대표자이름\",\"address\":\"회사주소\",\"businessNumber\":\"사업자정보\",\"businessType\":\"업태\",\"businessItems\":\"종목\",\"contacts\":[{\"name\":\"contact name\",\"email\":\"contact@email.com\",\"phone\":\"contact phone\"}]}";

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

> 문서 생성일 : 2019-09-27

