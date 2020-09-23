# 앱 정보/목록 조회

## Request
```
GET https://api.solapi.com/appstore/v2/me/apps
```

내가 등록한 앱의 정보/목록을 조회 할 수 있습니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `appstore:read` | `role-appstore:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| appId | `string` |  | eq | 앱 아이디 |
| appName | `string` |  | eq | 앱 이름 |
| categories | `array` |  | eq | 카테고리 |
| status | `string` |  | eq | 상태값 |
| dateSort | `string` |  | eq | 날짜 정렬 |
| type | `string` |  | eq | 설명 없음 |

---

## Samples

### (User) 앱 정보 및 목록 조회

> **Sample Request**

```
http://api.solapi.com/appstore/v2/me/apps
```

> **Sample Response**

```json
[
    {
        "thumbnail": {
            "name": "2BTZ6HLmal6x1Ao.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
            "originalName": null
        },
        "profit": {
            "sms": 1,
            "lms": 1,
            "mms": 1,
            "ata": 1,
            "cta": 1,
            "cti": 0
        },
        "apphomeConfig": {
            "primaryColor": null,
            "secondaryColor": null,
            "sideMenu": true,
            "slogan": true
        },
        "appVersion": "1.0.1",
        "screenshots": [
            {
                "name": "57PKHgfBolSgvN7.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
            },
            {
                "name": "RaAB8w6tlC0hYow.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
            }
        ],
        "homepage": "http://developer.example.com",
        "categories": [
            "BUSINESS",
            "ENTER"
        ],
        "intro": "Test App",
        "description": "Description Of App",
        "stage": "LIVE",
        "status": "ACTIVE",
        "reasonBlocked": null,
        "email": "test@testemail.com",
        "log": [],
        "appDomain": null,
        "customDomain": null,
        "type": "APP",
        "appName": "Test App 0",
        "accountId": "12925149",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "3JfTIsK2RiXC",
        "dateCreated": "2020-09-23T02:34:52.813Z",
        "dateUpdated": "2020-09-23T02:34:52.813Z",
        "redirectUri": "http://get.ms.coolsms.co.kr",
        "scope": [
            "message:read",
            "message:write"
        ]
    },
    {
        "thumbnail": {
            "name": "2BTZ6HLmal6x1Ao.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
            "originalName": null
        },
        "profit": {
            "sms": 1,
            "lms": 1,
            "mms": 1,
            "ata": 1,
            "cta": 1,
            "cti": 0
        },
        "apphomeConfig": {
            "primaryColor": null,
            "secondaryColor": null,
            "sideMenu": true,
            "slogan": true
        },
        "appVersion": "1.0.1",
        "screenshots": [
            {
                "name": "57PKHgfBolSgvN7.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
            },
            {
                "name": "RaAB8w6tlC0hYow.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
            }
        ],
        "homepage": "http://developer.example.com",
        "categories": [
            "BUSINESS",
            "ENTER"
        ],
        "intro": "Test App",
        "description": "Description Of App",
        "stage": "LIVE",
        "status": "ACTIVE",
        "reasonBlocked": null,
        "email": "test@testemail.com",
        "log": [],
        "appDomain": null,
        "customDomain": null,
        "type": "APP",
        "appName": "Test App 1",
        "accountId": "12925149",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "VOo8Q1iRyD4Z",
        "dateCreated": "2020-09-23T02:34:52.816Z",
        "dateUpdated": "2020-09-23T02:34:52.816Z",
        "redirectUri": "http://get.ms.coolsms.co.kr",
        "scope": [
            "message:read",
            "message:write"
        ]
    },
    {
        "thumbnail": {
            "name": "2BTZ6HLmal6x1Ao.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
            "originalName": null
        },
        "profit": {
            "sms": 1,
            "lms": 1,
            "mms": 1,
            "ata": 1,
            "cta": 1,
            "cti": 0
        },
        "apphomeConfig": {
            "primaryColor": null,
            "secondaryColor": null,
            "sideMenu": true,
            "slogan": true
        },
        "appVersion": "1.0.1",
        "screenshots": [
            {
                "name": "57PKHgfBolSgvN7.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
            },
            {
                "name": "RaAB8w6tlC0hYow.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
            }
        ],
        "homepage": "http://developer.example.com",
        "categories": [
            "BUSINESS",
            "ENTER"
        ],
        "intro": "Test App",
        "description": "Description Of App",
        "stage": "LIVE",
        "status": "ACTIVE",
        "reasonBlocked": null,
        "email": "test@testemail.com",
        "log": [],
        "appDomain": null,
        "customDomain": null,
        "type": "APP",
        "appName": "Test App 2",
        "accountId": "12925149",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "qrGTU1KO5evP",
        "dateCreated": "2020-09-23T02:34:52.819Z",
        "dateUpdated": "2020-09-23T02:34:52.819Z",
        "redirectUri": "http://get.ms.coolsms.co.kr",
        "scope": [
            "message:read",
            "message:write"
        ]
    },
    {
        "thumbnail": {
            "name": "2BTZ6HLmal6x1Ao.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
            "originalName": null
        },
        "profit": {
            "sms": 1,
            "lms": 1,
            "mms": 1,
            "ata": 1,
            "cta": 1,
            "cti": 0
        },
        "apphomeConfig": {
            "primaryColor": null,
            "secondaryColor": null,
            "sideMenu": true,
            "slogan": true
        },
        "appVersion": "1.0.1",
        "screenshots": [
            {
                "name": "57PKHgfBolSgvN7.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
            },
            {
                "name": "RaAB8w6tlC0hYow.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
            }
        ],
        "homepage": "http://developer.example.com",
        "categories": [
            "BUSINESS",
            "ENTER"
        ],
        "intro": "Test App",
        "description": "Description Of App",
        "stage": "LIVE",
        "status": "ACTIVE",
        "reasonBlocked": null,
        "email": "test@testemail.com",
        "log": [],
        "appDomain": null,
        "customDomain": null,
        "type": "APP",
        "appName": "Test App 3",
        "accountId": "12925149",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "wjgv3SGImg5M",
        "dateCreated": "2020-09-23T02:34:52.827Z",
        "dateUpdated": "2020-09-23T02:34:52.827Z",
        "redirectUri": "http://get.ms.coolsms.co.kr",
        "scope": [
            "message:read",
            "message:write"
        ]
    },
    {
        "thumbnail": {
            "name": "2BTZ6HLmal6x1Ao.png",
            "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0AkOPXsfoC/thumbnails/2BTZ6HLmal6x1Ao.png",
            "originalName": null
        },
        "profit": {
            "sms": 1,
            "lms": 1,
            "mms": 1,
            "ata": 1,
            "cta": 1,
            "cti": 0
        },
        "apphomeConfig": {
            "primaryColor": null,
            "secondaryColor": null,
            "sideMenu": true,
            "slogan": true
        },
        "appVersion": "1.0.1",
        "screenshots": [
            {
                "name": "57PKHgfBolSgvN7.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/0s_jELg_bR/screenshots/57PKHgfBolSgvN7.png"
            },
            {
                "name": "RaAB8w6tlC0hYow.png",
                "url": "https://coolsms-apps-images.s3.ap-northeast-2.amazonaws.com/IIZUEoZg0n/screenshots/RaAB8w6tlC0hYow.png"
            }
        ],
        "homepage": "http://developer.example.com",
        "categories": [
            "BUSINESS",
            "ENTER"
        ],
        "intro": "Test App",
        "description": "Description Of App",
        "stage": "LIVE",
        "status": "ACTIVE",
        "reasonBlocked": null,
        "email": "test@testemail.com",
        "log": [],
        "appDomain": null,
        "customDomain": null,
        "type": "APP",
        "appName": "Test App 4",
        "accountId": "12925149",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "fdtPARHvVAut",
        "dateCreated": "2020-09-23T02:34:52.830Z",
        "dateUpdated": "2020-09-23T02:34:52.830Z",
        "redirectUri": "http://get.ms.coolsms.co.kr",
        "scope": [
            "message:read",
            "message:write"
        ]
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
  url: 'http://api.solapi.com/appstore/v2/me/apps'
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
$url = "http://api.solapi.com/appstore/v2/me/apps";

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

url = "http://api.solapi.com/appstore/v2/me/apps"
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
	http://api.solapi.com/appstore/v2/me/apps
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps")

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
  uri := "http://api.solapi.com/appstore/v2/me/apps"

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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps";

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

