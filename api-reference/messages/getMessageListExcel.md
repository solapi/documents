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
"PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q}���0\u0001\u0000\u0000�\u0003\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml���N�0\u0010E%�\u0016%nY ��v�c\t�(\u001f0ؓĪ_�LK��8I+��H ��q�̜�ș-v�\u0016[Ld��Ŵ��\u0002�\n���\u0016o���V\u0014��5��\u0016{$���V��T�^O��㝔�:t@U��s҄��6�2�ZC��z2��*xF�%�3�|��\rl,\u0017���~t- Fk\u0014p֒y�(\u001ew9\u001c-���A���\u0013�� R%�C\ru&��) ��\u0013^�IF�\u0010�i�B\u001d��喊bB��!��հV\u000e�\u001f�KH�\f.O�;+?BZ����\u000e'�~O\u0018���\u000f!�a�^΃xo��I��\u0005�\u001d$ԯ��\r?/��O\u001e�˦B�2��&6gN�M�9%�\u0017\u001e�r���PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0003\u0000\u0000\u0000xl/PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000e\u0000\u0000\u0000xl/worksheets/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q��?Y\u0018\u0002\u0000\u0000o\u0006\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml��oo�0\u0010ƿ����I�t @j���`��i{m\u001c�XĹ�6�ݧ��\u0000#v4��g����9�2:���s�$\u001b�v9(���\u0018��=�0z�Y��85�\u0018\u0012�Y�%�\u001d(xnO\u0012P�\u001a\u001b�\u001dх�4��dF� �\u0013IE~R\u0018J�\u0019\u0011I��P|a \u000bj�Vd¼WZg\u0019�\u0019\u0015H\u0012��\f�A��Թ(�YE�u*\n}V�j�\u0014�`\n4$�c�8���\rȀX�&�Xطh+�\u0014O��!\u001cn\"L&���-�Q_��N�P\"^��[_C��\u0006l\u0001���*\u001e�\u0000#%v��\u0005k��*�\u000b 2Z�%\f���eՙ��Bw|M��P��>�\t\u0011/�yeڋB[��\u0014�?\"6i�c\u0014�\u001e2�\u0003�K^fcw���f���H�\u0011��\u0004]��ðk\ra��C�]%o\u001f�v�u\u0012�ȫ͂��G�\b���'�&1�n�x�^����]�X�D�I,}�I�|�k�x��A����c�\u0005q\\ݴ �l%����F���|\u0001Ǳ�\u0016ılڂ8��n#O-����\u0005q.ɢF��z��~�\u0013\r�^��-���<� n�o��[\u0010�fo��Rw�\\}Ѕ�\u001b\u001b�v\"�(�gO��4�Nk\u0003E���h\u000bƀ<G���\\�Q\u0017�\u0004���r�\\�1�\u000fPK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0006\u0000\u0000\u0000_rels/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q&��j�\u0000\u0000\u0000�\u0001\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels��Mj\u00031\f��b��h�E(%N6��])�\u0001T[�Ì-#;mr��BKSR�R�{���ٝ�l�Y�(�²i�pt���[x=>-\u001e��B��,�-\\8�n�y�J��aL�TF�\u0016�R�#bv\u0003\u0007ʍ$�u҉\u0006*��\u001e\u0013��z�UۮQ3��i\u000eނ\u001e�\u0012���\u001e�t��x/�\u00148�\u001b+�(*���b�<���&25\u0015\nx;���,�߉�\u000by*�N�\u0017I�[�X��\u0013ǋ{�����\u000e�W\u001f�~\u0002PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q��*\b\u0002\u0001\u0000\u0000�\u0001\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml��Ok�0\fſ��q<�\u0018!I/c����\u001dGiLl�X��~�9i�\u0006���'\u001e�!=�����\u0007\"\u0019�\r�E�\u0019x���}��^9����,zh�\u0005�����q�\u0011g�t�\u001d<F����3g���SJ�\u0012��\u0004NQ�\u0001|vF�N��ƃ�\u0010A\r4\u0001$g�SY�\b���\u0011*�\u001f�8\u0015�c�itA%�\u001bk�eem��\b\u0005��hxC}t��u�\b6\u0013��d\u0002m�|�\u001d�\u0019\u001d�pLE�↺;N�B��}m�D�m�DI.�hk��Z��ʼr9�U���EtC�\u0019g�2Y�n�|Alsbc��PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000xl/_rels/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q\u0011gy��\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels��Mk�0\f@���}q��\u0018�n/c�k?~���84����˿����@\u0007;�$��{\u000f�\\��:Q�>\u0006\u0003MU��`��Cg��xz\u0005ł��\u0010\u0003\u0019��a�Zni@)_���Ua\u00046�Eқ�l=��UL\u0014ʦ�yD)�����\u001d�E]��|ˀ9Sm���q\u000bP{�\u001d�\u0001����$�4�\n���D��ƶ�-�G�9R�;v=���\u001f�|\u0013#�@������o~�瘏��Z^F��\u001f�5FϮ��\u0000PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000docProps/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q\u000b&`|7\u0001\u0000\u0000�\u0002\u0000\u0000\u0011\u0000\u0000\u0000docProps/core.xml��]O�0\u0014��J����@!�6\u00125\\I4\u0011\"�iϠq�H[\u001d�{�\u0001\u0003\"^yټO����l�j�\r�K�\u000bL�\u0004#��\b�7\u0005^-��\u0014#\u001f�\u0016�6\u001a\n�\u0007�ge�mƍ�Wg,� ��֣}�m��!،\u0010Ϸ���[B�ae�b�=�\r���\r�4I�\u0004\u000b�t��\u000eF|T\n>(헫{��\u0004jP��'4���\u0006p�߼�'\u0017��ao�&z\n\u0007z��\u00006M\u00137�\u001em�S�^<���FRw���\\��;`��r!�3�T\u0001�T��V\u001e\\N.�n�5�aѮ�� \u001e�]�\r�Ǒ\u000f2\u0010���\u001d\u0006;%�ǧ�\u001c�i�&\u0011�Q:Y�4��ft\u001c�G���˕�,UǇ�e=Iʾ���)\u0000PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q@�n�q\u0001\u0000\u0000�\u0002\u0000\u0000\u0014\u0000\u0000\u0000xl/sharedStrings.xml}��J�0\u001c�_��^�v�Mi+�����*λ�EWX��d2�ԩ\fv%V\u0010�D\u0010\u0014�\u000b��\n�B6}\u00073\u0006N;k�r~'�s\u0012���체�]j9D\u0003� \u0002\u0012&\u0005�h�-\r�\u001a�\u0003i Qf��Yv\b��.�`LW)eR��\u0012�\u0001E\u001c�\u0012k��'z��J�\u0006J�UF!��\u0012�M:�T0\u0011d�qm����\u0005i��f��0fv\u0019*\b\rC۴\b\u0010\u0011��2=��x��{\u0012?;�v�y*d�\n;�k�|y\r���9o���U��\b�_�,x���A�_�Eհ��/��2�N:1�wQ���\u0018�j�����A�\u001f^p�\u001f\u0017w�9���������\u001f����]���\u0011\u000e���\u0015CF\bE��k\n��(�R���䤑�g3������\\F��g~���H\"5�X2�W�s\u000b�\u0019%;�\u0018�3\\cQ\ru�tW\u0014M\u0019\u0013=\t�ϩ\u0001PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000G�{Q��o\u0006�\u0001\u0000\u0000S\u0003\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml���j�0\u0010�_E�^w�]��kl�\u00100��KS(�\u001edY�E5\u001a#iúOߑ�\t\u000bmu����7�\u0019����e��\u0007���}��v\n{�ƚ}jw�8\u000bQ�^Zt��\u000e���B\\��2i\u001d\u0019��qt�eg�~=��⌨.�|�q.�\bj� �\u001eg��2�\u0007\u0019��G\u0011f�e\u001f\u0012\t�8\u0016ŝ\u0000i�F(A�\u000f\u0004��y�w\na��tƚ�d�\u000b&��\u0004Fy\f8�=E\n\u001c\u0006�����,���r\u0017h!\u0006���\"��Ub�[\u001e��\u0006|��;\u0015�\u001f\u000b-\u0001 ��MS\tP������S�݉��\u0012\u001b��\u0006t��I�>�b�ҒrL�\n-z�Ǯ�m[�d'A�n\u000fҚΛ$\u000e\u0012�]��k%�-%4־&<�Uh*j`�޵ta��i��.G�_1��\u001fޣ�����M@�(o�����m���TV\u000f�\u0002�\u0019��G�E2�H�i���\u0011��\t�\u0012�\u001d\b���߆w\u0005]\u0007&��.-��X�<5?7�/����\u0002��m\u001emv��ޖ�N���7PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q}���0\u0001\u0000\u0000�\u0003\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000[Content_Types].xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0003\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000a\u0001\u0000\u0000xl/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000e\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\u0001\u0000\u0000xl/worksheets/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q��?Y\u0018\u0002\u0000\u0000o\u0006\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0001\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0006\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\u0003\u0000\u0000_rels/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q&��j�\u0000\u0000\u0000�\u0001\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0004\u0000\u0000_rels/.relsPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q��*\b\u0002\u0001\u0000\u0000�\u0001\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001e\u0005\u0000\u0000xl/workbook.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000M\u0006\u0000\u0000xl/_rels/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q\u0011gy��\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000t\u0006\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000G�{Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\u0007\u0000\u0000docProps/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q\u000b&`|7\u0001\u0000\u0000�\u0002\u0000\u0000\u0011\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0007\u0000\u0000docProps/core.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q@�n�q\u0001\u0000\u0000�\u0002\u0000\u0000\u0014\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000e\t\u0000\u0000xl/sharedStrings.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000G�{Q��o\u0006�\u0001\u0000\u0000S\u0003\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\n\u0000\u0000xl/styles.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\r\u0000\r\u0000\u0010\u0003\u0000\u0000�\f\u0000\u0000\u0000\u0000"
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

> 문서 생성일 : 2020-11-27

