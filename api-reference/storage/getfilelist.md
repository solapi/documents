# 파일 목록 조회

## Request

```text
GET https://api.solapi.com/storage/v1/files
```

한 계정이 가지고 있는 파일들의 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `storage:read` |  | `ACTIVE` | `ACTIVE` |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| fileId | `string` |  | eq | 파일 고유 아이디 |
| name | `string` |  | eq | 파일 이름 |
| url | `string` |  | eq | 파일 주소 |
| originalName | `string` |  | eq | 원본 파일 이름 |
| handleKey | `string` |  | eq | 참조의 핸들키 |
| category | `string` |  | eq | 참조 이름 |
| refId | `string` |  | eq | 참조 대상의 리소스 아이디 |
| dateCreated | `date` |  | eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq | 최근 수정 날짜 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| type | `string` |  | eq | 문서 타입\(DOCUMENT, KAKAO, MMS\) |
| useDaou | `boolean` |  | eq | \[카카오 채널\] 다우기술 이미지 연동 여부 |
| useBiztalk | `boolean` |  | eq | \[카카오 채널\] 비즈톡 이미지 연동 여부 |

## Samples

### getFileList.spec.js

> **Sample Request**

```text
http://api.solapi.com/storage/v1/files
```

> **Sample Response**

```javascript
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
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740209Jlb5GjGYvQj",
            "accountId": "19013037529548",
            "name": "파일 이름34",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740209Kpaf8l4t3hr",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740209wmLyuyO4n6U"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.210Z",
            "dateUpdated": "2020-09-23T03:27:40.210Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름33",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427402049266iGXmwgm",
            "accountId": "19013037529548",
            "name": "파일 이름33",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740204HSAqdb4jeyO",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740204xyYoWSC1zco"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.205Z",
            "dateUpdated": "2020-09-23T03:27:40.205Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름32",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740199shmXEHRKhuN",
            "accountId": "19013037529548",
            "name": "파일 이름32",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE2009230427401997nXwBsejVxo",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740199grzhRslzXZ2"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.200Z",
            "dateUpdated": "2020-09-23T03:27:40.200Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름31",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740194IijQSQWq1yo",
            "accountId": "19013037529548",
            "name": "파일 이름31",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740195p5C9j862Brx",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740195BjVRoU01gWd"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.195Z",
            "dateUpdated": "2020-09-23T03:27:40.195Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름30",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427401901qweMvniIEr",
            "accountId": "19013037529548",
            "name": "파일 이름30",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740190hCTRLOZClnQ",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740190RKS4gTdOxY3"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.191Z",
            "dateUpdated": "2020-09-23T03:27:40.191Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름29",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427401854RyuuslKtBv",
            "accountId": "19013037529548",
            "name": "파일 이름29",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740185BxSzGz3YgUb",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID52009230427401852TnZiVLhqt3"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.186Z",
            "dateUpdated": "2020-09-23T03:27:40.186Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름28",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740181lHEWumwfZms",
            "accountId": "19013037529548",
            "name": "파일 이름28",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE2009230427401810k172m8GSVB",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740181R1K5bDgynlE"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.182Z",
            "dateUpdated": "2020-09-23T03:27:40.182Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름27",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427401761HssPCyvaEJ",
            "accountId": "19013037529548",
            "name": "파일 이름27",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740176qk5YZgKFlFz",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740176xhFf3EKHZ33"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.177Z",
            "dateUpdated": "2020-09-23T03:27:40.177Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름26",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740171ECeETCzDNE7",
            "accountId": "19013037529548",
            "name": "파일 이름26",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740172DtIF6g0Pxsl",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740172VCXWFPhUXOT"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.173Z",
            "dateUpdated": "2020-09-23T03:27:40.173Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름25",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427401675IPYTUwZl7l",
            "accountId": "19013037529548",
            "name": "파일 이름25",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740167o43le7U75kv",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740167sR3Ea4HXKs9"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.168Z",
            "dateUpdated": "2020-09-23T03:27:40.168Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름24",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740162NNW03UrFqmf",
            "accountId": "19013037529548",
            "name": "파일 이름24",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740163g36uVEpTcnm",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740163dvcGc8YHdnf"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.164Z",
            "dateUpdated": "2020-09-23T03:27:40.164Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름23",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740156Qk8vCuRBBTj",
            "accountId": "19013037529548",
            "name": "파일 이름23",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740156R0YYV6bV5I2",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740156jh45BgvP68L"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.157Z",
            "dateUpdated": "2020-09-23T03:27:40.157Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름22",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740151IBG3RyOAwFM",
            "accountId": "19013037529548",
            "name": "파일 이름22",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE2009230427401513kXQDUIhtEo",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740151WDe8QDvbKr8"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.152Z",
            "dateUpdated": "2020-09-23T03:27:40.152Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름21",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740146Qc9e2ZJ3hjn",
            "accountId": "19013037529548",
            "name": "파일 이름21",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740146zx8Qxj0txaM",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID52009230427401467Vz6eNoAlZm"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.147Z",
            "dateUpdated": "2020-09-23T03:27:40.147Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름20",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740139eRXGV5ej4La",
            "accountId": "19013037529548",
            "name": "파일 이름20",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE2009230427401397DDaEdiGZXe",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740139FYDC94vuZc3"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.141Z",
            "dateUpdated": "2020-09-23T03:27:40.141Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름19",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID2009230427401349dHOz0Ijhlw",
            "accountId": "19013037529548",
            "name": "파일 이름19",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740134eeZlrhR2Gmz",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740135f6jdezZ33kd"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.136Z",
            "dateUpdated": "2020-09-23T03:27:40.136Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름18",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740129DqYbEDfj9QY",
            "accountId": "19013037529548",
            "name": "파일 이름18",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740129lmrdTcOydI6",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID520092304274012947URFgEL6Iu"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.131Z",
            "dateUpdated": "2020-09-23T03:27:40.131Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름17",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740125qraqqlTHij3",
            "accountId": "19013037529548",
            "name": "파일 이름17",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740125S2xKGOPNASw",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740125IE40qjoY8NW"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.126Z",
            "dateUpdated": "2020-09-23T03:27:40.126Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름16",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740120JPSJ8gNOc2h",
            "accountId": "19013037529548",
            "name": "파일 이름16",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740120CPXJg58Fwg3",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID52009230427401200BSbaqSlFfi"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.121Z",
            "dateUpdated": "2020-09-23T03:27:40.121Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름15",
            "link": null,
            "width": null,
            "height": null,
            "fileSize": null,
            "fileId": "FILEID200923042740114g9l4ZC03OPS",
            "accountId": "19013037529548",
            "name": "파일 이름15",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE200923042740114MEKLUadAAIo",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5200923042740114vELDr2yy0Uw"
                }
            ],
            "dateCreated": "2020-09-23T03:27:40.116Z",
            "dateUpdated": "2020-09-23T03:27:40.116Z"
        }
    ],
    "startKey": null,
    "nextKey": "FILEID200923042740109qd0lHHD2l09"
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
```text
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

> 문서 생성일 : 2020-09-23

