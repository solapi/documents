# 템플릿 목록 조회

## Request
```
GET https://api.solapi.com/kakao/v1/templates
```

템플릿의 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `kakao:read` | `role-kakao:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| name | `string` |  | eq, ne, like | 이름 |
| pfId | `string` |  | eq | 카카오톡채널 고유 아이디 |
| templateId | `string` |  | eq | 템플릿 고유 아이디 |
| status | `string` |  | eq | 상태값 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateCreated | `date` |  | eq, gte, lte, gt, lt | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq, gte, lte, gt, lt | 최근 수정 날짜 |

---

## Samples

### getTemplates.spec.js

> **Sample Request**

```
http://api.solapi.com/kakao/v1/templates
```

> **Sample Response**

```json
{
    "limit": 20,
    "templateList": [
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936039kdjBxrLYv00",
            "name": "A34",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.039Z",
            "dateUpdated": "2019-12-17T22:29:36.039Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936039TDg8yunlyRg",
            "name": "A33",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.039Z",
            "dateUpdated": "2019-12-17T22:29:36.039Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038zWwE6QgfGT4",
            "name": "A27",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038uqiUtL62rEC",
            "name": "A31",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038qi0ZdGGKnst",
            "name": "A32",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.039Z",
            "dateUpdated": "2019-12-17T22:29:36.039Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038eAV6XUT8sdy",
            "name": "A28",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038dhrGK8jdCBt",
            "name": "A25",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038bgeYOSLMcTv",
            "name": "A30",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038NZoSViwhHTD",
            "name": "A22",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038KDkun5zsjMP",
            "name": "A20",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038DDj2dmL25wL",
            "name": "A24",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038CJsb7EdUgMi",
            "name": "A19",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038CEYdRh7Yi6G",
            "name": "A26",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936038BNQGO1Tln7P",
            "name": "A29",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID19121722293603860I6iO8OCit",
            "name": "A18",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID1912172229360385ZV6nL2Y6O4",
            "name": "A23",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID1912172229360384FCE4c5b6o4",
            "name": "A17",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID1912172229360381CSqkyWvJO8",
            "name": "A21",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.038Z",
            "dateUpdated": "2019-12-17T22:29:36.038Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936037ze2gIz8GTFx",
            "name": "A3",
            "pfId": "PF01ID191217222935635Vh0Q0pKgcpb",
            "codes": [
                {
                    "status": "INSPECTING",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-27T22:29:35.634Z",
            "dateUpdated": "2019-12-27T22:29:35.634Z",
            "buttons": []
        },
        {
            "accountId": "12925149",
            "templateId": "TP01ID191217222936037utuulyqvJ6r",
            "name": "A15",
            "pfId": "PF01ID191217222935635a9FExVm7Fnz",
            "codes": [
                {
                    "status": "APPROVED",
                    "comments": [],
                    "service": "biz",
                    "code": "123123"
                }
            ],
            "content": "testMessage",
            "dateCreated": "2019-12-17T22:29:36.037Z",
            "dateUpdated": "2019-12-17T22:29:36.037Z",
            "buttons": []
        }
    ],
    "startKey": "TP01ID191217222936039kdjBxrLYv00",
    "nextKey": "TP01ID191217222936037rEHqN9XnCAj"
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
  url: 'http://api.solapi.com/kakao/v1/templates'
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
$url = "http://api.solapi.com/kakao/v1/templates";

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

url = "http://api.solapi.com/kakao/v1/templates"
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
	http://api.solapi.com/kakao/v1/templates
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates")

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
  uri := "http://api.solapi.com/kakao/v1/templates"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates";

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

> 문서 생성일 : 2019-12-17

