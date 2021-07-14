# 메시지 목록 엑셀다운로드

## Request
```
GET https://api.solapi.com/messages/v4/list/excel
```

메시지의 목록을 다운로드합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| criteria | `string` |  | eq | 검색 조건에 사용되는 필드명<br>criteria 의 값은 'key1,key2,key3' 과 같이 ,(콤마) 로 구분되며 cond, value 와 함께 사용됩니다.<br>- messageId - 메시지 아이디 입니다.<br>- groupId - 그룹 아이디 입니다.<br>- to - 수신 번호 입니다.<br>- from - 발신 번호 입니다.<br>- type - 문자 메시지의 타입 입니다.  (SMS, LMS, MMS, ATA, CTA, CTI)<br>- dateCreated - 그룹 생성일 입니다.<br>- dateUpdated - 그룹 정보를 변경한 마지막 시각 입니다.<br>- replacement - 대체 발송 여부 입니다. (true, false)<br>- statusCode - 문자 메시지의 상태 코드 입니다. |
| cond | `string` |  | eq | 검색 조건에 사용되는 연산자<br>criteria 와 같이 'cond1,cond2' 와 같이 ,(콤마)로 구분되며, criteria,value 와 함께 사용됩니다.<br>- eq - 같음 (=)<br>- ne - 같지 않음 (!=)<br>- gt - 보다 큼 (>)<br>- gte - 보다 크거나 같음 (>=)<br>- lt - 보다 작음 (<)<br>- lte - 보다 작거나 같음 (<=) |
| value | `string` |  | eq | 검색 값<br>criteria , cond 값에 대응하는 value 입니다.<br>criteria='messageId,statusCode'<br>cond='eq,eq'<br>일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다.<br>e.g - value='메시지아이디,2000' |
| subAccountId | `string` |  | eq | 설명 없음 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateType | `string` |  | eq | 설명 없음 |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

---

## Samples

### 발송내역 엑셀 다운로드

> **Sample Request**

```
http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```

> **Sample Response**

```json
"PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml��]s� \u0000E�\n�{%$ƯI��ֺ�}����3\u00124�!d\u0000���;I0\u001b�n�\u0017E\u000f�B.�F�\u0017��3S��\"�x�A�\n*S^\u001cb����a\u0001�6�HI.\u000b\u0016�O��c\u0012UR\u001duƘ\u0001\u0017�\u0017:��1�\n!M3&��Ȓ\u0015\u0017��\u0012��T\u0007�K�H�H\"G��͐ ��m�Jݓ!�{N�Zғ`�iC\u0014ˉ��\u0019/�5M�{�\u0004Q�S�@�(��;�s�لB �j{(�\"�������^��\u000f7�S%�ܛ\t�\u0002�\u001b�}�%Z\"Ba\u00125=��ҽ1�k�Iy��6��\u0007Q\u0012������\u000f\u0005R�'��|��+���\u0010�\u00104\u001b\\��k�)+L\f��\u001f�IT�y\u0005�ק\r� ����b�g\u0010Г6R��_X�\u0015|+�\u0010X!��\n�\u0015�{��\u0015�����\u0015B+��\n3+�:��FW�[a�\t����¢\u0013��\u0005�v�����\u0005�g�zp=��=��q����Q{I�;�&�$��\u0015P�-I\"Z\u000f�`\bL\f5L�s�E�D�Z��g�e�}�l�g��^�l�M��.��g3�����e�>[��ϖ.{�3��\u0018�dյ�w-��\u0016�'\u0007\u000e�zvࠬ�\u0003\u0007m����\u0003�]:pX�\u0003\u0007�ց���\u001c80��\u0001�>�_������(�\rPK\u0007\b�\tG/ \u0002\u0000\u0000�\u0006\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml��MO\u00021\u0010��Jӫ�\u0005\u000f�\u0018\u0016\u000e~\u001c�D�\u0001�vv���6�\u0001�ov��\u0018�\u000b�9�;��4�|�Ǡ�X�'���L�B����V�s�2�׊\u0005�AH���!��b��ed��@\\�N$?X�u�\u0011ؤ���Ф\u0012Aؤ��\f�\u001aZ���靭\u0013\t�Ld�Ћ�\u00136�\t��{A�{\u0014\f���>8�*\r9\u0007_��DvK�\u000fer ��a�p�3��1h{�0l�\u0007\u001c�޶X�w�ޡ�+D����Ne���ڜ/9a�����R��Hb8\u0017\u0004�\u001d��`�i\"x:z��a��]Ydx�X|��e\u0017��\fߗ^\"wP�}H��^]�w��Î\u001f~�\u0003PK\u0007\bCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels��AN�0\u0010��X�'��@\b��B�\u0016�\u0003\u0018g�X�g,�[�۳%\u0012\u000b�O��?�[��NE���S׃!�2\u0007^-|N�O�`�:�]\u0014&\u000b\u000fR8��\u0007EW��n!�i)�Z�j�o��7JN;��-�EJrU;)+f�w�\u0012>��\u000b��\u0006\u001cMs�-��|\u00023=2�ǖe\t�.�o���q��\u0005�ɕ���\u0016�[��%�w-E�q�C��\u0003PK\u0007\b��닱\u0000\u0000\u0000'\u0001\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml���n�0\u0010�_��{�!\u0001�\b\u0013�J��R否g\u0017/���m\ny�\n\u0010J{�i��O�u�\u001f�\"�輴�A��@�TVHse�q~}ʁ�����\u001adpG\u000f��譻}Y{#�V�3hBhwQ�\u00065�+ۢ\u0019����<��u�ȷ\u000e��\rb�*J(�\"ͥ���s�aغ�\u0015\u001el�i4a�8T<Hk|#[\u000feQK���\u000f�m��52\u0018\u0014\u0010�}x\u00112�`�\u0002Q��?����N*�`��k�\u001e%O�\b�y�¹A��\u0019��&I��9��\"���и��S\u001aa{\u0006��\u0002�/[F���˧\u0014�a\u0010��6]�7��&0�S����\u0017}��/�i\u00123�;���L�Q0����\u0014\f�Q�S~\tU\\U'G�1\u00197i�̎�;�\u001fPK\u0007\b�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml�TQo� \u0010�+��\u0004�K�&\u0002*%i�J�4���W�q�z�\u00058s6��O؎��\u000f��'����;8�]k\u0000\u001d�\u000f�Y��i���ҕ��\u0019�����b\u0014���\u0000g\u0015�'\u0015�\u001d�!�@=\u001d���5`\u0003Ç\u0018�%!A\u001e�\u0011a�je[\u0003��F�0u~OB�(CJ2@�,�!Fh�{���\u001f\u00011¿6�D:S��w\u001at<uX\u0018\u0019�|�[��\u000e\u0014�m>\u0013��m��\u001b-�\u000b��S�\fqU��z�rA\u0016DH�i�l\fH��F�s�:��u��6\u001d%g\u001f�i���\u0002\u0018�sL8�\u000e�G�JA�S+��#�\u0002���䬄�p��Ert�\u001c⌶�''I<�%pZi��U�\bh\u0000Nk\u0011��v�\u0001�`?�jŰuV�0]���^��b~�@����/�\u001f+'齋SPU$�z�?�5����\u0018�!��Z�\u0015���3\u0006#p*\u0015�Sz\\/�\u001b�B�1[\u0013\u001fJ�3�R\u0013Φ\u0006\u0018�\u001e��$�k�\u001e�Ӱ��F�7���GX]�w�^�k�o4��Qz.\fO�\u0004x�@�FC�v�s�\u001b8-�K\u0007�t�1\rF�۱J�Q�*�@|\u001e\u000f\u0019���T�\u001bS�Q?���\u000e����.:�I5T\u001b\u001fC�V�x�������~[Ln���d�E�'��j3��֫�f�Ȋl��jN?1��o�i�ϖ\u0001�T~\u0010;H|��\u0018�����'��4Yg\u0011����PK\u0007\b�c��E\u0002\u0000\u0000)\u0005\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels���J\u00031\u0010E%̻��\n\"Ҵ/E諮\u001f\u0010��$4��L�ݿ\u0017\nj\u0017���ǹ\u0017�=0�������!����A �l\u00039\u0005o���#\bn����P��\f���\u0005�n!\u0013�PX�)\u0012+�')�xL��\\��\u0014�\\�n���d��\u001d�M�?�zɀ5S\u001c��z�\u0003�q)�\u001fv��`��{BjW&�g�'��\rĨ�æ�'byn�nN\u0011�u��-e�����@��V�_2�7�iK�K���=/W��}\u0001PK\u0007\b/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000#\u0000\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsU�A\u000e� \u0010\u0000����\u000bՃ1���>��\u00036tm��KXb��^u\u001e0��s2o�\u001a�=\u001c�\u0000�8�\u001ay��/�\u000b\u0018m�+&a��!�y\u001ao��Ea�cQ�sb���V��i�)�Z)�=��ԌM���\u0015\f/�ȝ�����\u0001�����\u000bPK\u0007\b����{\u0000\u0000\u0000�\u0000\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000`9�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0014\u0000\u0000\u0000xl/sharedStrings.xmlu�[K\u0002A\u0018���0��3�\u001a�\u001bYt��d��-:���9c�]���U`\u0010��B\u0017QWQR\u0006�\"g�\u000faс\t��y���^Ɯ��\u001e8\"U�\u0006Ԃ8�  �\u0010\u0014]Z��Nnq*\u0005\u0001�\u000e-:^@�\u0005�\t����\u0018\u0007uߣ̂e�+3��\ne�;,\u0016T\b���AP�\u001d�bA���J�8EV&����#4���K!(\u00045�-�S\u0010Ԩ{X#�?�m2�6�=|i��\u0012\f_\"\u0019F�5��\u001a�Mm��\u0014�Б�Pޟ\u0000yٔݞ�tTe��\u0017wx\ne{�yٺ�̢P<>�m�'����Ɖ�=W]\u0019]�\u000b�\u0003�\u000e����\t�q:j�����.��z\u0002\u001bi5_3vu�S(��\u0018#d\u0018\u000b�|>���W7��W2X����(��'�㛹�����쒞]�P}����H}sR�j�#\u001d��&Hʛ\u000e���\u000e\u0000N�v\b0\u0012�M�H�^�wGc��\u001fPK\u0007\bb\u0012�+�\u0001\u0000\u0000�\u0002\u0000\u0000PK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R�\tG/ \u0002\u0000\u0000�\u0006\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0000\u0000\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�RCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��f\u0002\u0000\u0000[Content_Types].xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R��닱\u0000\u0000\u0000'\u0001\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0003\u0000\u0000_rels/.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0004\u0000\u0000xl/workbook.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R�c��E\u0002\u0000\u0000)\u0005\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��&\u0006\u0000\u0000xl/styles.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\b\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�R����{\u0000\u0000\u0000�\u0000\u0000\u0000#\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\t\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000`9�Rb\u0012�+�\u0001\u0000\u0000�\u0002\u0000\u0000\u0014\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\n\u0000\u0000xl/sharedStrings.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\b\u0000\b\u0000\u0013\u0002\u0000\u0000R\f\u0000\u0000\u0000\u0000"
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
  url:
    'http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq'
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
$url = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

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

url = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"
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
	http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq")

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
  uri := "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"

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
    String targetUrl = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

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

> 문서 생성일 : 2021-07-14

