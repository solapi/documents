# 앱 정보/목록 조회

## Request
```
GET https://api.solapi.com/appstore/v2/apps
```

로그인 하지 않은 사용자도 앱 정보/목록을 조회 할 수 있습니다.

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| offset | `number` |  | eq | 검색 시작 지점 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| accountId | `string` |  | eq | 계정 고유 아이디 |
| appId | `string` |  | eq | 앱 아이디 |
| appName | `string` |  | eq | 앱 이름 |
| categories | `array` |  | eq | 카테고리 |
| type | `string` |  | eq | 설명 없음 |

---

## Samples

### (Public) 앱 정보 및 목록 조회

> **Sample Request**

```
http://api.solapi.com/appstore/v2/apps
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
        "appId": "WPwDm120vRgv",
        "dateCreated": "2020-09-23T02:34:52.580Z",
        "dateUpdated": "2020-09-23T02:34:52.580Z",
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
        "appId": "3IsViEr1UZQx",
        "dateCreated": "2020-09-23T02:34:52.584Z",
        "dateUpdated": "2020-09-23T02:34:52.584Z",
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
        "appId": "lRhogkxxOpLi",
        "dateCreated": "2020-09-23T02:34:52.590Z",
        "dateUpdated": "2020-09-23T02:34:52.590Z",
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
        "appId": "skJuN8VKHRmD",
        "dateCreated": "2020-09-23T02:34:52.593Z",
        "dateUpdated": "2020-09-23T02:34:52.593Z",
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
        "appId": "hTn8ueXm8JtP",
        "dateCreated": "2020-09-23T02:34:52.597Z",
        "dateUpdated": "2020-09-23T02:34:52.597Z",
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
        "appName": "Test App 0",
        "accountId": "487",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "yXtQCmMijOan",
        "dateCreated": "2020-09-23T02:34:52.600Z",
        "dateUpdated": "2020-09-23T02:34:52.600Z",
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
        "accountId": "487",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "PfLC1RE64hIq",
        "dateCreated": "2020-09-23T02:34:52.605Z",
        "dateUpdated": "2020-09-23T02:34:52.605Z",
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
        "accountId": "487",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "R1bhRgZcDSaB",
        "dateCreated": "2020-09-23T02:34:52.609Z",
        "dateUpdated": "2020-09-23T02:34:52.609Z",
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
        "accountId": "487",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "feD8MoPvz4ki",
        "dateCreated": "2020-09-23T02:34:52.612Z",
        "dateUpdated": "2020-09-23T02:34:52.612Z",
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
        "accountId": "487",
        "clientId": "CIDNURIGOCOOLSMS",
        "appId": "7Ex2tGcfuPpo",
        "dateCreated": "2020-09-23T02:34:52.615Z",
        "dateUpdated": "2020-09-23T02:34:52.615Z",
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
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/appstore/v2/apps'
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
$url = "http://api.solapi.com/appstore/v2/apps";

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

url = "http://api.solapi.com/appstore/v2/apps"

response = requests.get(url)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	http://api.solapi.com/appstore/v2/apps
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/apps")

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
  uri := "http://api.solapi.com/appstore/v2/apps"

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
    String targetUrl = "http://api.solapi.com/appstore/v2/apps";

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

> 문서 생성일 : 2020-09-23

