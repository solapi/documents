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
"PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml���n�0\u0010�_%�}q\u0012\u000e-(�ږR�a�Z���8�D�qd�C߾�\u0013��*�\u001b���\u0019�c����2�H�Ly>w���:4'<N�����kys�:R�<�\u0019�����ҽ��\u0013\u0017{�P�\u001c��r�&J\u00153�$I(�r�\u000b�\u0003�r���G�C�\u0010\u0014Ǖ�e(�\tb8��:�L����۔�\u0005'\u0007FsU'\u00114�\n��IZ�6\u001b#}�1,���pV@�M���J�:��ֻ�\u000b��`�g�I��z�J�R\"��[5�t�n�z�S4E�)\n+\u001f���$��Sں�|_�u<w=\u0017E!�������pb�ŇL��\u0015Mw��\t��Ͳ�Y�����M�f\u0010��L�gP\u000e>\u001d��ӆm�s\u0015Oi�\u0012XM\\�\u001c���o�E#�\u0005A#��\b��N��\u0011@�'�tUK\u0010ۖ@��\u0012l�\u0012@�'�\u001dV\u0002�mKp�;*�6\u0002��\u0000ju�\u001e.LU\u0000b�\u0002�F\u0000������\u0012墑�0̎�J\\K`�J�A�N�v��\u0011\u0005�f����E#���L;t�k��.��\u0003\\݇\u0005V8\n\u0005?9���Í\"��\u001bl\u000f\u000e���c��\bׇ4�Ag��\u001eu\u0016�l���ɞt62�Rgc�=�lb���nM��ٝ�^t65٫�|˘7\u0003Zμ\u001bв�\u0001��A0��p��p�\u0018]��[n=\u0018в�р�_\u000b\u0003Z�=u��\u0001-;�\rh���a`��֡o)_��\u000e\u0003k\u0012o:�Ӿ�0�ǤCMY��~���\t]^��'PK\u0007\b�D��i\u0002\u0000\u0000\u001b\b\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml���NB1\u0010�_���Ђ\u000bc\f\u0007\u0016^�j\">����4��΀���\u001c 1\u0006aêig���6�η��\r\u0016r)6r��R`4ɺ�l���et/\u00051D\u000b>El�\u000eI�g��.#�:\u001b��\u001ds~КL�\u0001H���V�T\u0002pݖ��`V�D};\u001e�i�\"c�\u0011�\u0019r6}�\u0016֞��\u001e�=\nz��q�س\u001a\t9{g����D��2:\u0010T�\u001cz�s�n���'\t}��a�>Lq\u0016�;\u0014~�P5����TV_)����\u0013��m�A��:�\u0017P�\u000b��\u000e��Wê\u0002�x�>�\u001f�I\u000f���\"����\u000b\u001e�;�te�>�\u0012�����K��W\u0017��}��Ç��\u0000PK\u0007\bCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels���\n�0\f\u0007�W)��L\u000f\"�n\u0017\u0011v��\u0000��>Xה������@�\u0018���IQ-�\u0011/�ad+a�� �jnG�K�7��\tD�ʶʰ%\t+\u0005���FFŴ\u0012��\u0005�\f\u001b$\f1�3b�\u0003�*d�ȦN�~V1��G���z�C�\u001f�\u001b�5E�J�u�\u0007Ѭ.�����FM\u0017�ϙl�\u0011�ۉ$+�S��\u0018|��\u001e�S�\u000e\u0006,\u000b�<X~\u0000PK\u0007\b��닰\u0000\u0000\u0000'\u0001\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml�Q�n�0\u0010�\u0015k�%\u000fH\u0014P\u0002RE�r�z�pv�\r�p��v\u001a��n\u0012E���ֳ���l��5�}�u��\u0002�E\b\fui�ԗ\u0002>��O\u00190�\u0016\\\u0019�\u0005���n���^���2\u001a׮���v\u0013\u0004����naZ�T��m�'h/�k-r�jDߨ \u000e�4h��01l�8LU�\u0012���\u001a�~\"�����]-[\u0007ۼ�\nO�\u001e����7��M\u0001S��\u0017!=�\u0002\u0012���?\t۵ϝTT]/�%\u0004\u000f�\u001f�\t�x�������V���t�\u001c�8I��ch��v�Z���UF��g�\u0012���Y\n_\u0013S\u0016�i�)���R�\u0002�$L\u0006��\u0017��\u001f�2F�Gq{�9\u001dip�@�G��F��\u001eD4��C%W%i\u0019�ظJ�x�Ϲ�\u0001PK\u0007\b�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml�TM��0\u0010�+���@�m\u0012\u0001+%�H+m�J�J�:`\u0012k��l��V��\u001d\u0003�D{�J{�3����\u0019�ǋ\u0014�̌�Z�8��\u00181�낫c�_��`��uT\u0015Th�R�0�\u001f�ĺF�݉1�\u0000@�\u0014��������$�\u0013]1\u0005;�6�:p͑��0ZXH\n\u0012��\u0003��+�!,e�\u0011\u0010I�[]\u0005��\u0015u��\u0005wM���̗�G�\r=\b z��4�b��;x�s��.�\u0004��.K���,\u0017dA\u0000)KJ��E���\u0003�\u0000�߰|S����-\u001f�@���L\u0005D\"L�$�B\u001b�@\u0019 �F\u0014���XS�\u000f����J.�.\u001c�@+f�'9�����\u0017\u000b��\u0010\u0003��\u0013�@��:�\u0019�\u0005\u0007�����z\u0005����y��>\u001a�D���\u0000i/̒�6\u0005�ͨ�5�%��\u000e�\u001a~<���\n�\u0007�\u001c��%\u0005�G��\u0000�t �\u0001��L��o���\u001d��D��[鞋\u0014C�z\u0011�&\u0014қ\u001d^�x�[�\u000e�Ӱ�R\u000e�w���GX�\u001eo�\u0001����j\u001e�#�.)��I@��\fС��q5�\u0019�\u0005��2*\u0018�\u0007t~0Zm�[@Ȃ��\u0016n?l�x�����2\u001e�~�v-D�G��?t���`\u0017�b�;aE��)�����<m�`\u001e����\u000b�\u0005��j\u0013̦��f�]�q��{3�����o�%0�K+`�M_l_�n������-\u000e��k�E\u0010;��PK\u0007\b�c��G\u0002\u0000\u0000)\u0005\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels���j�0\f�_��8�`�Q��1�\u001e@�J\u001c�������k\n�\u0016(ۥGI��}H���8�\u0013e�c0�T5(\n6�>t\u0006\u000e���WP,\u0018\u001c\u000e1���\u0018֫�\u0006��¾O�\n#�\u0001/�޴f�iD�b�P&m�#J)s�\u0013�#v�\u0017u���o\u0006̙j�\f�k@��Tr�gǶ�-�G�9R�;\u0011�\u001c�=�\u0014(������:i�b\f����2�1��I.��\u001f�Y�/����4�������;^Ͼ��\u0000PK\u0007\b/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000#\u0000\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsU�A\u000e\u0002!\f�᫐�\u001dЅ1\u0006��\u00070z�f�\u0002�)�\u0012����._�����-�\u00175I�\u001d�'\u0003�x)k���~��N��#��\u000b��\u000f\t��^)c\u001f\u0017���\u001a\u0006���{=k-K�\re*�x�Gi\u001b�1[�\u0015�'\u0006�\u0007c���\u001a��C�\u0017PK\u0007\b����{\u0000\u0000\u0000�\u0000\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u0000#U7R\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0014\u0000\u0000\u0000xl/sharedStrings.xmlu�]O�0\u0014�����\u0011�\t\u001fEI��ר\u0006c\"���E�G#5N�݉�1\u001a�J\\M\u000b\u0012��)�$\u0010�.�Q\u0018H�\u001fj���;&@��;��{�sl���n�\u0004oi�\u0007\u0011s �B\u0010PV��\u0001�v�\u000bo��\u001c\u0004\\���7#F\u001d��r��ڜ\u000b�*\u0019w`C�ּa�Z��>��Z�)�&j��P����[m��y�R\u00116\r�Ќ\u0011�\u0001��\u0016u�p 1!�`�C\u0017�\u0004�\"pm�\u000e�c�\u001d��y&�,��\u001b\u001d_نpmc�o-�Y\"\u000fSy�\u0007�Q,��<It���U�����ޱ<,���\u0016����|�w\u001bu���\u0003]���q��\u001f5�\u0004�׿��\u0007�\u000f\u0017r�\u0007����d�=Wg?�'��4�>1��\u001fuӢ�[xw�z$&%2�����[/\t�s�D�\u0018#dYK^�Z)��O7��^+cݿ����K��\u0013s�{��j}��J*k�t?R����\u0004�\u0015���\t\"8?�\u0001�_\u0012@Lu�\u0000��k\u0000\u000b�1����^��-꒷����\r�\u001b�\u001bPK\u0007\b9�8�\u0001\u0000\u0000J\u0003\u0000\u0000PK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R�D��i\u0002\u0000\u0000\u001b\b\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0000\u0000\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7RCpE\u001e\u001b\u0001\u0000\u0000/\u0003\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0002\u0000\u0000[Content_Types].xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R��닰\u0000\u0000\u0000'\u0001\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u000b\u0004\u0000\u0000_rels/.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R�j�v=\u0001\u0000\u0000\u0010\u0002\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0004\u0000\u0000xl/workbook.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R�c��G\u0002\u0000\u0000)\u0005\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��n\u0006\u0000\u0000xl/styles.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R/��\u0002�\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\b\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R����{\u0000\u0000\u0000�\u0000\u0000\u0000#\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0010\n\u0000\u0000xl/worksheets/_rels/sheet1.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u0000#U7R9�8�\u0001\u0000\u0000J\u0003\u0000\u0000\u0014\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\n\u0000\u0000xl/sharedStrings.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\b\u0000\b\u0000\u0013\u0002\u0000\u0000�\f\u0000\u0000\u0000\u0000"
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

> 문서 생성일 : 2021-01-23

