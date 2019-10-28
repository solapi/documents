# 파일 목록 조회

## Request
```
GET https://api.solapi.com/storage/v1/files
```

한 계정이 가지고 있는 파일들의 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `storage:read` |  | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| fileId | `string` |  | eq | 파일 고유 아이디 |
| name | `string` |  | eq | 이름 |
| url | `string` |  | eq | 파일 주소 |
| originalName | `string` |  | eq | 파일 이름 |
| handleKey | `string` |  | eq | 참조의 핸들키 |
| category | `string` |  | eq | 참조 이름 |
| refId | `string` |  | eq | 참조 대상의 리소스 아이디 |
| dateCreated | `date` |  | eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq | 최초 생성 날짜 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| type | `string` |  | eq | 설명 없음 |
| useDaou | `boolean` |  | eq | 설명 없음 |
| useBiztalk | `boolean` |  | eq | 설명 없음 |

---

## Samples

### getFileList.spec.js

> **Sample Request**

```
http://api.solapi.com/storage/v1/files
```

> **Sample Response**

```json
{
    "fileList": [
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름34",
            "link": null,
            "fileId": "FILEID191028182513538XECPXD8Qoe3",
            "accountId": "19013037529548",
            "name": "파일 이름34",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513538aHpGTaMll2D",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513538f0OfFZo4rEq"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.541Z",
            "dateUpdated": "2019-10-28T18:25:13.541Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름33",
            "link": null,
            "fileId": "FILEID191028182513530EJ3uiVvhRpp",
            "accountId": "19013037529548",
            "name": "파일 이름33",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513530hptsJdDC6G4",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513530jLizemfy3fx"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.531Z",
            "dateUpdated": "2019-10-28T18:25:13.531Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름32",
            "link": null,
            "fileId": "FILEID1910281825135239mI45gVBhHj",
            "accountId": "19013037529548",
            "name": "파일 이름32",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE1910281825135243Qv3lwWd8V5",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513524WwxFW33c3yt"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.524Z",
            "dateUpdated": "2019-10-28T18:25:13.524Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름31",
            "link": null,
            "fileId": "FILEID1910281825135182dz3fzuC8Y1",
            "accountId": "19013037529548",
            "name": "파일 이름31",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513518fbXkc7QJ5ib",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513518ObVOQ7NEonK"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.519Z",
            "dateUpdated": "2019-10-28T18:25:13.519Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름30",
            "link": null,
            "fileId": "FILEID191028182513512BqPSU162zjk",
            "accountId": "19013037529548",
            "name": "파일 이름30",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513512tQHTvKnLd5k",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51910281825135121mO98hdzeQl"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.513Z",
            "dateUpdated": "2019-10-28T18:25:13.513Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름29",
            "link": null,
            "fileId": "FILEID19102818251350744ZeLs9RBnX",
            "accountId": "19013037529548",
            "name": "파일 이름29",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513507DCXoxqqnkXg",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513507MRSSr2mi4FS"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.508Z",
            "dateUpdated": "2019-10-28T18:25:13.508Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름28",
            "link": null,
            "fileId": "FILEID191028182513485gaTTI929qtX",
            "accountId": "19013037529548",
            "name": "파일 이름28",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513485O0n1nXC6o35",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513485iHmnq0FwbQ7"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.496Z",
            "dateUpdated": "2019-10-28T18:25:13.496Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름27",
            "link": null,
            "fileId": "FILEID191028182513478ecM9NYAzrdj",
            "accountId": "19013037529548",
            "name": "파일 이름27",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513478mcFSkqrrPxC",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513478XCIxUjTIJe4"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.479Z",
            "dateUpdated": "2019-10-28T18:25:13.479Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름26",
            "link": null,
            "fileId": "FILEID191028182513473ssFpPuiPdeV",
            "accountId": "19013037529548",
            "name": "파일 이름26",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513473ryXP7yNbrsq",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51910281825134731NvaIirauGF"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.474Z",
            "dateUpdated": "2019-10-28T18:25:13.474Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름25",
            "link": null,
            "fileId": "FILEID191028182513465aNUTpw9XOEu",
            "accountId": "19013037529548",
            "name": "파일 이름25",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513466JOBVVGTi98A",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51910281825134662tMCc3foUak"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.467Z",
            "dateUpdated": "2019-10-28T18:25:13.467Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름24",
            "link": null,
            "fileId": "FILEID191028182513430ysLUbMBj4eC",
            "accountId": "19013037529548",
            "name": "파일 이름24",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513430B5FksThMUYD",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513430UM0VNrupOaw"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.431Z",
            "dateUpdated": "2019-10-28T18:25:13.431Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름23",
            "link": null,
            "fileId": "FILEID191028182513425dgT7siNbaiG",
            "accountId": "19013037529548",
            "name": "파일 이름23",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513425GjBiyLny3zi",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513425PeTreoghvqS"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.425Z",
            "dateUpdated": "2019-10-28T18:25:13.425Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름22",
            "link": null,
            "fileId": "FILEID191028182513420TP8dg2TxXOU",
            "accountId": "19013037529548",
            "name": "파일 이름22",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513420UtIaWPtyQmG",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513420h8oqAnzeGTE"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.421Z",
            "dateUpdated": "2019-10-28T18:25:13.421Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름21",
            "link": null,
            "fileId": "FILEID191028182513416YB5fjwnCok1",
            "accountId": "19013037529548",
            "name": "파일 이름21",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513416nPCRUgXToDX",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513416AL3Q3fOLOrD"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.417Z",
            "dateUpdated": "2019-10-28T18:25:13.417Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름20",
            "link": null,
            "fileId": "FILEID191028182513411tIF9xnEHQuc",
            "accountId": "19013037529548",
            "name": "파일 이름20",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE1910281825134123IZakL9RrhQ",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513412XluJi0tFjdT"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.412Z",
            "dateUpdated": "2019-10-28T18:25:13.412Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름19",
            "link": null,
            "fileId": "FILEID191028182513407lvPHqr6OgXJ",
            "accountId": "19013037529548",
            "name": "파일 이름19",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513407hts4SxxjMlV",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513407naqOOazBowr"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.408Z",
            "dateUpdated": "2019-10-28T18:25:13.408Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름18",
            "link": null,
            "fileId": "FILEID191028182513403K9VbnjWUSJ1",
            "accountId": "19013037529548",
            "name": "파일 이름18",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513403xktrbOkjfZP",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513403DzHFKT7ekUO"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.404Z",
            "dateUpdated": "2019-10-28T18:25:13.404Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름17",
            "link": null,
            "fileId": "FILEID191028182513398sx9Bsg8gPOK",
            "accountId": "19013037529548",
            "name": "파일 이름17",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513398bDaxpKCBuWY",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513398onhDAeRrzrq"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.399Z",
            "dateUpdated": "2019-10-28T18:25:13.399Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름16",
            "link": null,
            "fileId": "FILEID191028182513392hslFhcUh4vh",
            "accountId": "19013037529548",
            "name": "파일 이름16",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513393GNpfewciMVT",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513393Kzh6fMshhPz"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.394Z",
            "dateUpdated": "2019-10-28T18:25:13.394Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름15",
            "link": null,
            "fileId": "FILEID191028182513387oB4NgblnzHm",
            "accountId": "19013037529548",
            "name": "파일 이름15",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191028182513387EGS07eqU0jU",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191028182513387wTFyLyq9JZa"
                }
            ],
            "dateCreated": "2019-10-28T18:25:13.388Z",
            "dateUpdated": "2019-10-28T18:25:13.388Z"
        }
    ],
    "startKey": null,
    "nextKey": "FILEID191028182513383qeThtuwOI7K"
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
  url: 'http://api.solapi.com/storage/v1/files'
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
  url: 'http://api.solapi.com/storage/v1/files'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/storage/v1/files";

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

url = "http://api.solapi.com/storage/v1/files"
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
	http://api.solapi.com/storage/v1/files
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/storage/v1/files")

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
  uri := "http://api.solapi.com/storage/v1/files"

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
    String targetUrl = "http://api.solapi.com/storage/v1/files";

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

> 문서 생성일 : 2019-10-28

