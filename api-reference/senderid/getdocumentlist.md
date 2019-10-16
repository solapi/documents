# 문서 목록 조회

## Request

```text
GET https://api.solapi.com/senderid/v1/documents
```

문서 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `senderid:read` | `role-senderid:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| documentId | `string` |  | eq | 문서 ID |
| startDate | `string` |  | eq | 검색 날짜 시작 범위 |
| endDate | `string` |  | eq | 검색 날짜 끝 범위 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| category | `string` |  | eq | 문서 카테고리 |
| use | `boolean` |  | eq | 문서 사용 여부 |

## Samples

### getDocumentList.spec.js

> **Sample Request**

```text
http://api.solapi.com/senderid/v1/documents
```

> **Sample Response**

```javascript
{
    "data": [
        {
            "use": false,
            "documentId": "DOC20181042905615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042805615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042705615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042605615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042505615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042405615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.528Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042305615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.527Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042205615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.527Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042105615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.527Z"
        },
        {
            "use": false,
            "documentId": "DOC20181042005615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_APPROVAL",
            "dateCreated": "2019-09-26T06:21:54.527Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041905615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041805615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041705615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041605615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041505615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041405615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041305615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041205615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041105615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        },
        {
            "use": false,
            "documentId": "DOC20181041005615MMXDST163SYMMXV",
            "accountId": "12925149",
            "name": "p1rLY8HPqzEd5FP.png",
            "url": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/ymotD9u4eYMr/thumbnails/LL8nsWzZEEX5e0B.png",
            "originalName": "image.jpg",
            "category": "SENDERID_LIMITATION",
            "dateCreated": "2018-03-01T09:00:00.000Z"
        }
    ],
    "nextKey": "DOC20181040905615MMXDST163SYMMXV"
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
  url: 'http://api.solapi.com/senderid/v1/documents'
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  url: 'http://api.solapi.com/senderid/v1/documents'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/senderid/v1/documents";

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

url = "http://api.solapi.com/senderid/v1/documents"
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
    http://api.solapi.com/senderid/v1/documents
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/documents")

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
  uri := "http://api.solapi.com/senderid/v1/documents"

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
    String targetUrl = "http://api.solapi.com/senderid/v1/documents";

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

> 문서 생성일 : 2019-09-26

