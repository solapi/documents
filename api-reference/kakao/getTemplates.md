# 템플릿 목록 조회

#### Request
```
GET https://api.solapi.com/kakao/v1/templates
```

**Authorization 인증 필요**

템플릿의 목록을 조회합니다.

#### Query Params
| Name | Type | Required | Allowed Operator |Description |
| :--- | :--: | :------: | :--------------: |:---------- |
| name | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 이름 |
| pfId | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 플러스 친구 고유 아이디 |
| templateId | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 템플릿 고유 아이디 |
| status | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 상태값 |
| startKey | `string` |  | GT, LT, LTE, GTE, NE, LIKE | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | GT, LT, LTE, GTE, NE, LIKE | 한 페이지에 불러옥 목록 개수 |
| dateCreated | `date` |  | GT, LT, LTE, GTE, NE, LIKE | 최초 생성 날짜 |
| dateUpdated | `date` |  | GT, LT, LTE, GTE, NE, LIKE | 최초 생성 날짜 |

---

#### Sample Request

```json
{}
```

#### Sample Response

```json
{
    "limit": 20,
    "templateList": [
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780uO4Dbew3TB8",
            "name": "A19",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780qxPCEQd0iEd",
            "name": "A27",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780oAFEsQ3LJA8",
            "name": "A30",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780iBywiZHdNUB",
            "name": "A21",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780eVDNc57mxfn",
            "name": "A22",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780WSK1R0EQiBN",
            "name": "A29",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780UNqK1TQvaZP",
            "name": "A31",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780RRD5MYrtN1J",
            "name": "A23",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780Pz8Ya5CiSMH",
            "name": "A32",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780OqLtFiQgObA",
            "name": "A24",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780LKB0oT7JYdl",
            "name": "A26",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780KhgdTmZs0bh",
            "name": "A34",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780GQGTAFjLjpG",
            "name": "A20",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959780C4cZFPWC7kT",
            "name": "A25",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID1906120709597808jZnrZIGStM",
            "name": "A33",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID1906120709597807U7Z8ehAJz6",
            "name": "A28",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.780Z",
            "dateUpdated": "2019-06-12T06:09:59.780Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959779s2YYU7V5efy",
            "name": "A7",
            "pfId": "PF01ID190612070959143wlkXuzY6A4g",
            "content": "testMessage",
            "dateCreated": "2019-06-22T06:09:59.142Z",
            "dateUpdated": "2019-06-22T06:09:59.142Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959779rRpTYvDutOM",
            "name": "A18",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.779Z",
            "dateUpdated": "2019-06-12T06:09:59.779Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959779pU545sWAwm4",
            "name": "A17",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.779Z",
            "dateUpdated": "2019-06-12T06:09:59.779Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190612070959779mJF32rzusxr",
            "name": "A16",
            "pfId": "PF01ID190612070959143sOx0PFcrLsv",
            "content": "testMessage",
            "dateCreated": "2019-06-12T06:09:59.779Z",
            "dateUpdated": "2019-06-12T06:09:59.779Z",
            "buttons": [],
            "comments": []
        }
    ],
    "startKey": "TP01ID190612070959780uO4Dbew3TB8",
    "nextKey": "TP01ID190612070959779jjwtR9oSPCL"
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
  url: 'http://api.solapi.com/kakao/v1/templates'
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
  url: 'http://api.solapi.com/kakao/v1/templates'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
$url = "http://api.solapi.com/kakao/v1/templates";
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

url = "http://api.solapi.com/kakao/v1/templates"
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
	http://api.solapi.com/kakao/v1/templates
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates")

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
  uri := "http://api.solapi.com/kakao/v1/templates"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates";

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

