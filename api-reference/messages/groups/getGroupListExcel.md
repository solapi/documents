# 그룹 목록 엑셀 다운로드

## Request
```
GET https://api.solapi.com/messages/v4/groups/excel
```

메시지 그룹 목록을 엑셀 다운로드합니다.

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
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateType | `string` |  | eq | 설명 없음 |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

---

## Response

### Response Structure
```json
{
    "startKey": "string",
    "limit": "number",
    "nextKey": "string",
    "groupList": {
        "groupId": {
            "count": {
                "total": "number",
                "sentTotal": "number",
                "sentFailed": "number",
                "sentSuccess": "number",
                "sentPending": "number",
                "sentReplacement": "number",
                "refund": "number",
                "registeredFailed": "number",
                "registeredSuccess": "number"
            },
            "balance": {
                "requested": "number",
                "replacement": "number",
                "refund": "number",
                "sum": "number"
            },
            "point": {
                "requested": "number",
                "replacement": "number",
                "refund": "number",
                "sum": "number"
            },
            "app": {
                "profit": {
                    "sms": "number",
                    "lms": "number",
                    "mms": "number",
                    "ata": "number",
                    "cta": "number",
                    "cti": "number"
                },
                "appId": "string",
                "version": "string"
            },
            "sdkVersion": "string",
            "osPlatform": "string",
            "log": [
                {
                    "message": "object",
                    "createAt": "date"
                }
            ],
            "status": "any",
            "scheduledDate": "date",
            "dateSent": "date",
            "dateCompleted": "date",
            "isRefunded": "boolean",
            "flagUpdated": "boolean",
            "groupId": "string",
            "accountId": "string",
            "apiVersion": "string",
            "countForCharge": {
                "sms": {
                    "country": "number"
                },
                "lms": {
                    "country": "number"
                },
                "mms": {
                    "country": "number"
                },
                "ata": {
                    "country": "number"
                },
                "cta": {
                    "country": "number"
                },
                "cti": {
                    "country": "number"
                }
            },
            "price": {},
            "dateCreated": "date",
            "dateUpdated": "date"
        }
    }
}
```

### Response Description
##### Response / 

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| startKey | `string` |  | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | 한 페이지에 불러옥 목록 개수 |
| nextKey | `string` |  | 다음 목록을 불러올 수 있는 키 |
| [groupList](#response-grouplist) | `object` |  | 그룹 목록 |

##### Response / groupList

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [groupId](#response-grouplist-groupid) | `string` |  | 그룹 아이디 |

##### Response / groupList / groupId

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [count](#response-grouplist-groupid-count) | `object` |  | 카운트 |
| [balance](#response-grouplist-groupid-balance) | `number` |  | 잔액 |
| [point](#response-grouplist-groupid-point) | `number` |  | 포인트 |
| [app](#response-grouplist-groupid-app) | `object` |  | 앱 정보 |
| sdkVersion | `string` |  | SDK 버전 |
| osPlatform | `string` |  | OS / Platform |
| [log](#response-grouplist-groupid-log) | `Array` |  | 로그 |
| status | `any` |  | 그룹 상태<br>PENDING - 대기중<br>SENDING - 이미 발송 요청된 그룹<br>DELETED - 삭제 처리된 그룹<br>FAILED - 실패 처리된 그룹<br>COMPLETE - 발송 완료된 그룹<br>SCHEDULED - 발송 예약된 그룹 |
| scheduledDate | `date` |  | 설명 없음 |
| dateSent | `date` |  | 발송 일시 |
| dateCompleted | `date` |  | 완료 일시 |
| isRefunded | `boolean` |  | 환급 여부 |
| flagUpdated | `boolean` |  | 업데이트 여부 |
| groupId | `string` |  | 그룹 아이디 |
| accountId | `string` |  | 계정 고유 번호 |
| apiVersion | `string` |  | API 버전 |
| [countForCharge](#response-grouplist-groupid-countforcharge) | `object` |  | 차감 카운트 |
| [price](#response-grouplist-groupid-price) | `any` |  | 단가 |
| dateCreated | `date` |  | 생성 일시 |
| dateUpdated | `date` |  | 업데이트 일시 |

##### Response / groupList / groupId / count

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| total | `number` |  | 토탈 |
| sentTotal | `number` |  | 전체 발송 건수 |
| sentFailed | `number` |  | 발송 실패 건수 |
| sentSuccess | `number` |  | 발송 성공 건수 |
| sentPending | `number` |  | 대기 건수 |
| sentReplacement | `number` |  | 대체 발송 건수 |
| refund | `number` |  | 환급 건수 |
| registeredFailed | `number` |  | 접수 실패 건수 |
| registeredSuccess | `number` |  | 접수 성공 건수 |

##### Response / groupList / groupId / balance

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| requested | `number` |  | 차감 금액 |
| replacement | `number` |  | 대체 발송 금액 |
| refund | `number` |  | 환급 금액 |
| sum | `number` |  | 합계 금액 |

##### Response / groupList / groupId / point

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| requested | `number` |  | 차감 포인트 |
| replacement | `number` |  | 대체 발송 포인트 |
| refund | `number` |  | 환급 포인트 |
| sum | `number` |  | 합계 포인트 |

##### Response / groupList / groupId / app

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [profit](#response-grouplist-groupid-app-profit) | `object` |  | 앱 사용 요금 |
| appId | `string` |  | 앱 아이디 |
| version | `string` |  | 앱 버전 |

##### Response / groupList / groupId / app / profit

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| sms | `number` |  | SMS 사용 요금 |
| lms | `number` |  | LMS 사용 요금 |
| mms | `number` |  | MMS 사용 요금 |
| ata | `number` |  | 알림톡 사용 요금 |
| cta | `number` |  | 친구톡 사용 요금 |
| cti | `number` |  | 친구톡 이미지 사용 요금 |


##### Response / groupList / groupId / log

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| message | `object` |  | 로그 메시지 |
| createAt | `date` |  | 로그 기록 일시 |

##### Response / groupList / groupId / countForCharge

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| [sms](#response-grouplist-groupid-countforcharge-sms) | `object` |  | SMS 차감 금액 |
| [lms](#response-grouplist-groupid-countforcharge-lms) | `object` |  | LMS 차감 금액 |
| [mms](#response-grouplist-groupid-countforcharge-mms) | `object` |  | MMS 차감 금액 |
| [ata](#response-grouplist-groupid-countforcharge-ata) | `object` |  | 알림톡 차감 금액 |
| [cta](#response-grouplist-groupid-countforcharge-cta) | `object` |  | 친구톡 차감 금액 |
| [cti](#response-grouplist-groupid-countforcharge-cti) | `object` |  | 친구톡 이미지 차감 금액 |

##### Response / groupList / groupId / countForCharge / sms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 SMS 차감 금액 |

##### Response / groupList / groupId / countForCharge / lms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 LMS 차감 금액 |

##### Response / groupList / groupId / countForCharge / mms

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 MMS 차감 금액 |

##### Response / groupList / groupId / countForCharge / ata

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 알림톡 차감 금액 |

##### Response / groupList / groupId / countForCharge / cta

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 친구톡 차감 금액 |

##### Response / groupList / groupId / countForCharge / cti

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |
| country | `number` |  | 국가별 친구톡 이미지 차감 금액 |

##### Response / groupList / groupId / price

| Name | Type | Should Return | Description |
| :--- | :--: | :-----------: | :---------- |


---

## Samples

### 메시지 그룹 목록 get /messages/v4/groups

> **Sample Request**

```
http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25
```

> **Sample Response**

```json
"PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q}���0\u0001\u0000\u0000�\u0003\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml���N�0\u0010E%�\u0016%nY ��v�c\t�(\u001f0ؓĪ_�LK��8I+��H ��q�̜�ș-v�\u0016[Ld��Ŵ��\u0002�\n���\u0016o���V\u0014��5��\u0016{$���V��T�^O��㝔�:t@U��s҄��6�2�ZC��z2��*xF�%�3�|��\rl,\u0017���~t- Fk\u0014p֒y�(\u001ew9\u001c-���A���\u0013�� R%�C\ru&��) ��\u0013^�IF�\u0010�i�B\u001d��喊bB��!��հV\u000e�\u001f�KH�\f.O�;+?BZ����\u000e'�~O\u0018���\u000f!�a�^΃xo��I��\u0005�\u001d$ԯ��\r?/��O\u001e�˦B�2��&6gN�M�9%�\u0017\u001e�r���PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0003\u0000\u0000\u0000xl/PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000e\u0000\u0000\u0000xl/worksheets/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q~%O�z\u0003\u0000\u0000G\u0017\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml��]o�0\u0014��J��5$� @�Zo��M�6m�&8$j\u0012G�)�~��\u0000]�s��]�<\u001c�\u0018���˃T�m.�\u000e�t񰫥�R���x��0x�ʺ]����\"��4\u0017\u0015o�d#j�&����\f�.j\u001b%���T�Q2\u001aM��\u0017��¢J�\u0014��z�7\u001fRY5\\\u0017��,���ֹ�\u001aREfY��{��+Q��Z�(MEY�yѴ�j�#�X\u0015������Yǩ\u0018ԛG��l�z�-̷��t�D�\no�\u0005K�a�^��B\u001c�w�A���gUl\u001f�Z���à�\u00056R>w�\u001f��p\u0014\u0006�����|\u0014�����~���]����N�tg��N<�?r���YP\u0004V��ߵ'\u0015lx+�d������`+2�/�wy�\"�՘��V�\\��R�C�z���ݿ$^L̆���m7ۯ�|�5�/��2z1�HO�GH�6q\u0007��&�!qm\u0013\f\u0012�7\"2\u0006o\u001a\t����O\u001d\rH�\u001c\rHL\u001c\r�`>�ҸF5�I\rH�\u001a�p5H��\bKc�j�I\rH�\u001a�p5H��\bKc�jLH\rH�\u001a�p5H��\bKc�jLI\rH�\u001a�p5H��\bKc�j�H\rH�\u001a�p5H��\bK�\u0006ո!5 �j@�� \t�#,�9�1'5 �j@�� \t�#,�.,��\u001b�\"\b� ȍ\u001b�\u0010��\u0019\b�K2\u0017�\u001c�(��\b��\b��\b���%\u0019<�c:�\u0011\u0004�@\u0004�@\u0004�\f��\u0018\u000f��Nv\u0004\u00012t��\b�\"�\f\u001e�1��\b\u0002d脧\u0011�El\u0019<�c:�\u0011\u0004��9O#̋�2x��t�#\b��ӞF�\u0017�e�����G\u0010 Cg>�0/b��\u001fӹ� @�N~\u001aa^Ė��?��\u001fA�\f��4¼�}r�;���\u0000\u0010\u0004\u001c\u001e}�}:=�\b�\"�\f�\u0001$t\u0007� @Ɨ�'\u0019\u0012a^Ė�p�\u001fp�\u001fp�\u001fp�\u001fp�\u001f�\u0001$x\u0007��\u001d\u0000�\u0000\u0019�\u0003�\u0011�El\u0019�\u0003H�\u000e\u0000A�\f�\u0001�\b�\"�\f�\u0001$t\u0007� @��\u0000h�y\u0011[\u0006�\u0000\u0012�\u0003@\u0010 Cw\u00004¼�Q&zwO����ծ�۠<^�^�N���g-�����Fj-��(\u0017|+T72�LJ}\u001et��ow��PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0006\u0000\u0000\u0000_rels/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q&��j�\u0000\u0000\u0000�\u0001\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels��Mj\u00031\f��b��h�E(%N6��])�\u0001T[�Ì-#;mr��BKSR�R�{���ٝ�l�Y�(�²i�pt���[x=>-\u001e��B��,�-\\8�n�y�J��aL�TF�\u0016�R�#bv\u0003\u0007ʍ$�u҉\u0006*��\u001e\u0013��z�UۮQ3��i\u000eނ\u001e�\u0012���\u001e�t��x/�\u00148�\u001b+�(*���b�<���&25\u0015\nx;���,�߉�\u000by*�N�\u0017I�[�X��\u0013ǋ{�����\u000e�W\u001f�~\u0002PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q��*\b\u0002\u0001\u0000\u0000�\u0001\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml��Ok�0\fſ��q<�\u0018!I/c����\u001dGiLl�X��~�9i�\u0006���'\u001e�!=�����\u0007\"\u0019�\r�E�\u0019x���}��^9����,zh�\u0005�����q�\u0011g�t�\u001d<F����3g���SJ�\u0012��\u0004NQ�\u0001|vF�N��ƃ�\u0010A\r4\u0001$g�SY�\b���\u0011*�\u001f�8\u0015�c�itA%�\u001bk�eem��\b\u0005��hxC}t��u�\b6\u0013��d\u0002m�|�\u001d�\u0019\u001d�pLE�↺;N�B��}m�D�m�DI.�hk��Z��ʼr9�U���EtC�\u0019g�2Y�n�|Alsbc��PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000xl/_rels/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q\u0011gy��\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels��Mk�0\f@���}q��\u0018�n/c�k?~���84����˿����@\u0007;�$��{\u000f�\\��:Q�>\u0006\u0003MU��`��Cg��xz\u0005ł��\u0010\u0003\u0019��a�Zni@)_���Ua\u00046�Eқ�l=��UL\u0014ʦ�yD)�����\u001d�E]��|ˀ9Sm���q\u000bP{�\u001d�\u0001����$�4�\n���D��ƶ�-�G�9R�;v=���\u001f�|\u0013#�@������o~�瘏��Z^F��\u001f�5FϮ��\u0000PK\u0003\u0004\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000docProps/PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q����6\u0001\u0000\u0000�\u0002\u0000\u0000\u0011\u0000\u0000\u0000docProps/core.xml��]k�0\u0014��J�}�����V؆W�\r�l�.$�5�� �V��K�Ve�j��p���=�\u0014��l�o�NhU�4!(\u0002�4\u0017�)�f��g(r�*N[��D{phQ\u0015��L[x�ڀ�\u0002\\\u0014<��̔h��1vl\u000b��$\u0010*\u0014km%��j\u001bl(��\r���;,�SN=Ž06�\u0011\u001d���J�e�A�\u0019�\u0016$(�p����z���l\u0018*\u0017�\u0014~o�&z*��Ή\u0011�.�&\u0003\u001a��}��:�\u001a\u000b�o�\u0001�\n�rf�zm��`V;]�蹮\u0005�h��\u0016����R�Wa��\u0000~����7X\u001cG>ȀG!j~\u0018�Ty�<<����HFb2\u000fgM�yF�t�d��G���q���C���$Ր���T?PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Qx9=�\u0001\u0001\u0000\u0000�\u0001\u0000\u0000\u0014\u0000\u0000\u0000xl/sharedStrings.xml�����Q(K-*��ϳU2�3PRH�K�O��K�U\n\rqӵPR(.I�KI���K�U�L-V���)..QH�/�+\u0001�\u0001j)��,,MuF\b\u0000M�+�U�())���/N�H�M,��/H�\u0003ʤ�\u0017�&�\u0000�E���\u0005E��)�\u0019��%�9�F\u0006\u0006f����yJ@+2�lJ�^mny�`�«�\u000b��Y�zS��\u0019;l�K�l�A�\u0010%�\u0001�\n�7\u0001����\u0004�x��\u000fVx;�����o���˽�0�M�B���+^mh@��GQihdidjhb�n�\t�\u00000\\х�3�\u0010B���\u0003\u0000PK\u0003\u0004\n\u0000\u0000\u0000\b\u0000�\")Q[��Rh\u0001\u0000\u0000�\u0002\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml��MO� \u0010��\n�Q���\u001eL�xV\u0013�S\n]��\u0010@���;��+\u001e���w�}`�T7'��դ�(�r��Ja��ޅ���\u000f�ٕ\u0014�@�\u0001)�Z�&˛��eDs4�\b�\u000fwC�\u0004\u001dr��;\u0007-\u0005SC�屔xP*��7\u0014M�����6\r*�d��\u0013ɣ�o��ʃ\u000b+��� \u001e��K<��#\u0014�9te�Y\u001f��V�H��D�lٰS��N��\u0017�V׊[j*K�d��%\u0014��*�(��+ +{��J\u0013R\u0012i�jٶ����\u0000�,e���Kn\u0012-x���\u0004�\u0010�9�\u0010?\u000f��Eh*\u0014Zވu�0F�}�?�`�?��\u0004�n��0\u0007>�������\"5\u0015\u001a[ؐ�p�b���d)<���\u001d\f\u0014\u0000'�c]0V\u001b�'�\u0003{�\u0002bı�E\u0011S�w}-硩�����ּ\u0003PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q}���0\u0001\u0000\u0000�\u0003\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000[Content_Types].xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0003\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000a\u0001\u0000\u0000xl/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000e\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\u0001\u0000\u0000xl/worksheets/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q~%O�z\u0003\u0000\u0000G\u0017\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0001\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0006\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000^\u0005\u0000\u0000_rels/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q&��j�\u0000\u0000\u0000�\u0001\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0005\u0000\u0000_rels/.relsPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q��*\b\u0002\u0001\u0000\u0000�\u0001\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0006\u0000\u0000xl/workbook.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\u0007\u0000\u0000xl/_rels/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q\u0011gy��\u0000\u0000\u00004\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u0007\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\u0000\u0000�\")Q\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\t\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000�\b\u0000\u0000docProps/PK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q����6\u0001\u0000\u0000�\u0002\u0000\u0000\u0011\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\n\t\u0000\u0000docProps/core.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Qx9=�\u0001\u0001\u0000\u0000�\u0001\u0000\u0000\u0014\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000o\n\u0000\u0000xl/sharedStrings.xmlPK\u0001\u0002\u0014\u0000\n\u0000\u0000\u0000\b\u0000�\")Q[��Rh\u0001\u0000\u0000�\u0002\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000�\u000b\u0000\u0000xl/styles.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\r\u0000\r\u0000\u0010\u0003\u0000\u00005\r\u0000\u0000\u0000\u0000"
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
    'http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25'
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
$url = "http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25";

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

url = "http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25"
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
	http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25")

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
  uri := "http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25"

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups/excel?criteria=dateCreated&value=2020-09-09%2013:20:20&cond=lt&limit=25";

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

> 문서 생성일 : 2020-09-09

