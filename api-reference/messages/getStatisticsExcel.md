# 통계 엑셀 파일 다운로드

## Request
```
GET https://api.solapi.com/messages/v4/statistics/excel
```

통계를 엑셀 파일로 만들어 다운로드합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |
| subAccountId | `string` |  | eq | 설명 없음 |

---

## Samples

### 통계 엑셀 다운로드

> **Sample Request**

```
http://api.solapi.com/messages/v4/statistics/excel?
```

> **Sample Response**

```json
"PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml���n�0\u0018F_��}q\u001c\b\u0005����R��,��1`5��m��\u001fe\u0003;\u001d��@�p~��\u0005��Q�`ϔ�2� �y\u0010��ʄg�\b��5�\u0019A�\r�\u0012�ʌE��4��ÃT_zØ\u0001G�f:�\u001bc�\u0013�4�0AtOnYv\u0014�J*A��I�Fz�\u0018I\nI����!\u0012�g��0Q]f�ՊS6�t'Xf�!���p��\r��z��]�\t��v�\u001b*Ŗ\u0018��)7�b(\u0004�N\u0016�L*�LY\u0004�x@h=�x�m��TI-W�G�@�B��y�ƈP\u0018�E\u000e8;h�\u001a�.����\"��\u0007Q\u001c�o��\u0015�~*��\u0015٥�<�\u0019_oL\u0004q\u0000A��Ir�2MYf\"��� �De��G x�6\u0004�\u001c��\u0003O�&��\u0007\u0001�i#���\r\\i��W�\u000fA7�_\t�� \u0012\u0006]��\u0012��\u0010��aX\tî�m%�v\u0015F�0�*�+a�U�^e�\u0017u\u0013����qg��\u001b[}_���pl5~E�+�V�W����f���v|��ߛ\u001d���8sSbH\u001c*y\u0000*?%qH�\u001f\u0018\u0002\u0013A\r�p\u001f{!��!�\u0015��\u0019vك�|�Mm�w٣�\u0006.��,pٓ͆.����e\u000b��\\�l���^l�\u001b��:��̛\u0003\u001bѼ;��͇\u0003\u001b�|:�\u000eR�p��?��[��F^�\u000el\u0004��\u0006�\u000el����F��6��\u0006�mp�\u0006�\u001d�X�K\u001b|u`c+om�\r~��O\u0007^V[\u0016\\�n�g\u0018�����\u0000PK\u0007\b\u000e\u001d\t~Y\u0002\u0000\u0000�\b\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml��MO\u00021\u0010��Jӫ�\u0005\u000f�\u0018\u0016\u000e~\u001c�D�\u0001�vv���6�\u0001�ov��\u0018�\u000b�9�;��4�|�Ǡ�X�'���L�B����V�s�2�׊\u0005�AH���!��b��ed��@\\�N$?X�u�\u0011ؤ���Ф\u0012Aؤ��\f�\u001aZ���靭\u0013\t�Ld�Ћ�\u00136�\t��{A�{\u0014\f���>8�*\r9\u0007_��DvK�\u000fer ��a�p�3��1h{�0l�\u0007\u001c�޶X�w�ޡ�+D����Ne���ڜ/9a�����R��Hb8\u0017\u0004�\u001d��`�i\"x:z��a��]Ydx�X|��e\u0017��\fߗ^\"wP�}H��^]�w��Î\u001f~�\u0003PK\u0007\bCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels��AN�0\u0010��X�'��@\b��B�\u0016�\u0003\u0018g�X�g,�[�۳%\u0012\u000b�O��?�[��NE���S׃!�2\u0007^-|N�O�`�:�]\u0014&\u000b\u000fR8��\u0007EW��n!�i)�Z�j�o��7JN;��-�EJrU;)+f�w�\u0012>��\u000b��\u0006\u001cMs�-��|\u00023=2�ǖe\t�.�o���q��\u0005�ɕ���\u0016�[��%�w-E�q�C��\u0003PK\u0007\b��닱\u0000\u0000\u0000'\u0001\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml���n�0\u0010�_��{�!\u0001�\b\u0013�J��R否g\u0017/���m\ny�\n\u0010J{�i��O�u�\u001f�\"�輴�A��@�TVHse�q~}ʁ�����\u001adpG\u000f��譻}Y{#�V�3hBhwQ�\u00065�+ۢ\u0019����<��u�ȷ\u000e��\rb�*J(�\"ͥ���s�aغ�\u0015\u001el�i4a�8T<Hk|#[\u000feQK���\u000f�m��52\u0018\u0014\u0010�}x\u00112�`�\u0002Q��?����N*�`��k�\u001e%O�\b�y�¹A��\u0019��&I��9��\"���и��S\u001aa{\u0006��\u0002�/[F���˧\u0014�a\u0010��6]�7��&0�S����\u0017}��/�i\u00123�;���L�Q0����\u0014\f�Q�S~\tU\\U'G�1\u00197i�̎�;�\u001fPK\u0007\b�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml�TQo� \u0010�+��\u0004�K�&\u0002*%i�J�4���W�q�z�\u00058s6��O؎��\u000f��'����;8�]k\u0000\u001d�\u000f�Y��i���ҕ��\u0019�����b\u0014���\u0000g\u0015�'\u0015�\u001d�!�@=\u001d���5`\u0003Ç\u0018�%!A\u001e�\u0011a�je[\u0003��F�0u~OB�(CJ2@�,�!Fh�{���\u001f\u00011¿6�D:S��w\u001at<uX\u0018\u0019�|�[��\u000e\u0014�m>\u0013��m��\u001b-�\u000b��S�\fqU��z�rA\u0016DH�i�l\fH��F�s�:��u��6\u001d%g\u001f�i���\u0002\u0018�sL8�\u000e�G�JA�S+��#�\u0002���䬄�p��Ert�\u001c⌶�''I<�%pZi��U�\bh\u0000Nk\u0011��v�\u0001�`?�jŰuV�0]���^��b~�@����/�\u001f+'齋SPU$�z�?�5����\u0018�!��Z�\u0015���3\u0006#p*\u0015�Sz\\/�\u001b�B�1[\u0013\u001fJ�3�R\u0013Φ\u0006\u0018�\u001e��$�k�\u001e�Ӱ��F�7���GX]�w�^�k�o4��Qz.\fO�\u0004x�@�FC�v�s�\u001b8-�K\u0007�t�1\rF�۱J�Q�*�@|\u001e\u000f\u0019���T�\u001bS�Q?���\u000e����.:�I5T\u001b\u001fC�V�x�������~[Ln���d�E�'��j3��֫�f�Ȋl��jN?1��o�i�ϖ\u0001�T~\u0010;H|��\u0018�����'��4Yg\u0011����PK\u0007\b�c��E\u0002\u0000\u0000)\u0005\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels���J\u00031\u0010E%̻��\n\"Ҵ/E諮\u001f\u0010��$4��L�ݿ\u0017\nj\u0017���ǹ\u0017�=0�������!����A �l\u00039\u0005o���#\bn����P��\f���\u0005�n!\u0013�PX�)\u0012+�')�xL��\\��\u0014�\\�n���d��\u001d�M�?�zɀ5S\u001c��z�\u0003�q)�\u001fv��`��{BjW&�g�'��\rĨ�æ�'byn�nN\u0011�u��-e�����@��V�_2�7�iK�K���=/W��}\u0001PK\u0007\b/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000#\u0000\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsU�A\u000e� \u0010\u0000����\u000bՃ1���>��\u00036tm��KXb��^u\u001e0��s2o�\u001a�=\u001c�\u0000�8�\u001ay��/�\u000b\u0018m�+&a��!�y\u001ao��Ea�cQ�sb���V��i�)�Z)�=��ԌM���\u0015\f/�ȝ�����\u0001�����\u000bPK\u0007\b����{\u0000\u0000\u0000�\u0000\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000K7�R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0014\u0000\u0000\u0000xl/sharedStrings.xml��MK\u0002A\u001cƿ�0�퐳J���F,\u0005�V�[�Xtʅ�Ysưkl\u0011�C\u001e\u0002�\u0004�\u000e\u001ez10\b�>��w�U��\u001a�>/��1�J���\u0011.Q7 :L&T\b0�\u0005y�\u001c�p�^�]��2��\u001d/ X�ǘ�\u0015C�����\u0011��\u0002c�e�h��}�&�\"&\u0015��\u000fJ��h\"(\u001d Z,a'O\u000b\u00183�C)U�G��\u0012\brA�0\u001d�T\b��=,cs,\u0018\u001au\r�\u0019��Nt\u001a\u001ab��be���P<�\u0000l����7�\f §�˫į����o~��w���\u0017��@�2��߷����lZ�=�N�u7#��k��\u001e�5��j��\u0006�5\u0006��a��gP\fw\u0000Ŵ7$�y�\u00127=�\u001c\u0002q����\u000f�p��i�\u0016eM\u000b�\t�Y�ړc�;�(�\u001c�3�4�ȱƝ�\u0011]�x�\u0003(q��NK(D���\u001e���ݵ��&{|JM%����sӿriZP��䷀(e�'PK\u0007\bX$���\u0001\u0000\u0000�\u0003\u0000\u0000PK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R\u000e\u001d\t~Y\u0002\u0000\u0000�\b\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0000\u0000\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�RCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0002\u0000\u0000[Content_Types].xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R��닱\u0000\u0000\u0000'\u0001\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0003\u0000\u0000_rels/.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0004\u0000\u0000xl/workbook.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R�c��E\u0002\u0000\u0000)\u0005\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��_\u0006\u0000\u0000xl/styles.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\b\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�R����{\u0000\u0000\u0000�\u0000\u0000\u0000#\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\t\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000K7�RX$���\u0001\u0000\u0000�\u0003\u0000\u0000\u0014\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\n\u0000\u0000xl/sharedStrings.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\b\u0000\b\u0000\u0013\u0002\u0000\u0000�\f\u0000\u0000\u0000\u0000"
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
  url: 'http://api.solapi.com/messages/v4/statistics/excel?'
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
$url = "http://api.solapi.com/messages/v4/statistics/excel?";

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

url = "http://api.solapi.com/messages/v4/statistics/excel?"
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
	http://api.solapi.com/messages/v4/statistics/excel?
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/statistics/excel?")

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
  uri := "http://api.solapi.com/messages/v4/statistics/excel?"

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
    String targetUrl = "http://api.solapi.com/messages/v4/statistics/excel?";

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

