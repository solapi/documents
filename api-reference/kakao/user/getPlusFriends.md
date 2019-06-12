# 플러스 친구 목록 조회

#### Request
```
GET https://api.solapi.com/kakao/v1/plus-friends
```

**Authorization 인증 필요**

플러스 친구의 목록을 조회합니다.

#### Query Params
| Name | Type | Required | Allowed Operator |Description |
| :--- | :--: | :------: | :--------------: |:---------- |
| pfId | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 플러스 친구 고유 아이디 |
| searchId | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 플러스 친구 검색용 아이디 |
| phoneNumber | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 핸드폰 번호 |
| dateCreated | `date` |  | GT, LT, LTE, GTE, NE, LIKE | 최초 생성 날짜 |
| dateUpdated | `date` |  | GT, LT, LTE, GTE, NE, LIKE | 최초 생성 날짜 |
| startKey | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | GT, LT, LTE, GTE, NE, LIKE | 한 페이지에 불러옥 목록 개수 |

---

#### Sample Request

```json
{}
```

#### Sample Response

```json
{
    "limit": 20,
    "friends": [
        {
            "pfId": "KA01PF190227072057634pRBhbpAweee",
            "searchId": "LG",
            "accountId": "19301859371111",
            "phoneNumber": "010-3333-3333",
            "dateCreated": "2019-06-12T06:53:24.537Z",
            "dateUpdated": "2019-06-12T06:53:24.537Z"
        },
        {
            "pfId": "KA01PF190227072057634pRBhbpAwddd",
            "searchId": "AMD",
            "accountId": "19301859371111",
            "phoneNumber": "010-5555-5555",
            "dateCreated": "2019-06-12T06:53:24.541Z",
            "dateUpdated": "2019-06-12T06:53:24.541Z"
        },
        {
            "pfId": "KA01PF190227072057634pRBhbpAwccc",
            "searchId": "SAMSUMG",
            "accountId": "19301859371111",
            "phoneNumber": "010-2222-2222",
            "dateCreated": "2019-06-12T06:53:24.536Z",
            "dateUpdated": "2019-06-12T06:53:24.536Z"
        },
        {
            "pfId": "KA01PF190227072057634pRBhbpAwbbb",
            "searchId": "NURIGO",
            "accountId": "19301859371111",
            "phoneNumber": "010-1111-1111",
            "dateCreated": "2019-06-12T06:53:24.534Z",
            "dateUpdated": "2019-06-12T06:53:24.534Z"
        },
        {
            "pfId": "KA01PF190227072057634pRBhbpAwaaa",
            "searchId": "INTEL",
            "accountId": "19301859371111",
            "phoneNumber": "010-4444-4444",
            "dateCreated": "2019-06-12T06:53:24.539Z",
            "dateUpdated": "2019-06-12T06:53:24.539Z"
        }
    ],
    "startKey": "KA01PF190227072057634pRBhbpAweee",
    "nextKey": null
}
```

#### Sample Code

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  url: 'http://api.solapi.com/kakao/v1/plus-friends?'
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
  url: 'http://api.solapi.com/kakao/v1/plus-friends?'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
$url = "http://api.solapi.com/kakao/v1/plus-friends?";
$data = array();

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
        'method'  => 'GET',
        'content' => http_build_query($data)
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

url = "http://api.solapi.com/kakao/v1/plus-friends?"
headers = {"Authorization":"Bearer eyJhbGciOiJI..."}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
curl -X GET \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/kakao/v1/plus-friends?
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/plus-friends?")

headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
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
  uri := "http://api.solapi.com/kakao/v1/plus-friends?"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/plus-friends?";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("x-is-admin", "true");

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

