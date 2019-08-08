# 그룹 목록 조회

> 문서 생성일 : 2019-08-07

## 그룹 목록 조회

### Request

```text
GET https://api.solapi.com/messages/v4/groups
```

메시지 그룹 목록을 조회합니다.

#### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` | O |

#### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| criteria | `string` |  | eq | 검색 조건에 사용되는 필드명 criteria 의 값은 'key1,key2,key3' 과 같이 ,\(콤마\) 로 구분되며 cond, value 와 함께 사용됩니다. - messageId - 메시지 아이디 입니다. - groupId - 그룹 아이디 입니다. - to - 수신 번호 입니다. - from - 발신 번호 입니다. - type - 문자 메시지의 타입 입니다.  \(SMS, LMS, MMS, ATA, CTA\) - dateCreated - 그룹 생성일 입니다. - dateUpdated - 그룹 정보를 변경한 마지막 시각 입니다. - replacement - 대체 발송 여부 입니다. \(true, false\) - statusCode - 문자 메시지의 상태 코드 입니다. |
| cond | `string` |  | eq | 검색 조건에 사용되는 연산자 criteria 와 같이 'cond1,cond2' 와 같이 ,\(콤마\)로 구분되며, criteria,value 와 함께 사용됩니다. - eq - 같음 \(=\) - ne - 같지 않음 \(!=\) - gt - 보다 큼 \(&gt;\) - gte - 보다 크거나 같음 \(&gt;=\) - lt - 보다 작음 \(&lt;\) - lte - 보다 작거나 같음 \(&lt;=\) |
| value | `string` |  | eq | 검색 값 criteria , cond 값에 대응하는 value 입니다. criteria='messageId,statusCode' cond='eq,eq' 일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다. e.g - value='메시지아이디,2000' |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |

### Response

#### Response Structure

```javascript
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
                    "cta": "number"
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
            "status": "string",
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
                }
            },
            "price": {},
            "dateCreated": "date",
            "dateUpdated": "date"
        }
    }
}
```

#### Response Description

#### Response /

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| startKey | `string` |  | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | 한 페이지에 불러옥 목록 개수 |
| nextKey | `string` |  | 다음 목록을 불러올 수 있는 키 |
| [groupList](getmessagegrouplist.md#response-grouplist) | `object` |  | 그룹 목록 |

#### Response / groupList

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| [groupId](getmessagegrouplist.md#response-grouplist-groupid) | `string` |  | 그룹 아이디 |

#### Response / groupList / groupId

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| [count](getmessagegrouplist.md#response-grouplist-groupid-count) | `object` |  | 카운트 |
| [balance](getmessagegrouplist.md#response-grouplist-groupid-balance) | `number` |  | 잔액 |
| [point](getmessagegrouplist.md#response-grouplist-groupid-point) | `number` |  | 포인트 |
| [app](getmessagegrouplist.md#response-grouplist-groupid-app) | `object` |  | 앱 정보 |
| sdkVersion | `string` |  | SDK 버전 |
| osPlatform | `string` |  | OS / Platform |
| [log](getmessagegrouplist.md#response-grouplist-groupid-log) | `Array` |  | 로그 |
| status | `string` |  | 그룹 상태 PENDING - 대기중 SENDING - 이미 발송 요청된 그룹 DELETED - 삭제 처리된 그룹 FAILED - 실패 처리된 그룹 SCHEDULED - 발송 예약된 그룹 COMPLETE - 발송 완료된 그룹 |
| scheduledDate | `date` |  | 예약 일시 |
| dateSent | `date` |  | 발송 일시 |
| dateCompleted | `date` |  | 완료 일시 |
| isRefunded | `boolean` |  | 환급 여부 |
| flagUpdated | `boolean` |  | 업데이트 여부 |
| groupId | `string` |  | 그룹 아이디 |
| accountId | `string` |  | 계정 고유 번호 |
| apiVersion | `string` |  | API 버전 |
| [countForCharge](getmessagegrouplist.md#response-grouplist-groupid-countforcharge) | `object` |  | 차감 카운트 |
| [price](getmessagegrouplist.md#response-grouplist-groupid-price) | `object` |  | 단가 |
| dateCreated | `date` |  | 생성 일시 |
| dateUpdated | `date` |  | 업데이트 일시 |

#### Response / groupList / groupId / count

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| total | `number` |  | 토탈 |
| sentTotal | `number` |  | 전체 발송 건수 |
| sentFailed | `number` |  | 발송 실패 건수 |
| sentSuccess | `number` |  | 발송 성공 건수 |
| sentPending | `number` |  | 대기 건수 |
| sentReplacement | `number` |  | 대체 발송 건수 |
| refund | `number` |  | 환급 건수 |
| registeredFailed | `number` |  | 접수 실패 건수 |
| registeredSuccess | `number` |  | 접수 성공 건수 |

#### Response / groupList / groupId / balance

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| requested | `number` |  | 차감 금액 |
| replacement | `number` |  | 대체 발송 금액 |
| refund | `number` |  | 환급 금액 |
| sum | `number` |  | 합계 금액 |

#### Response / groupList / groupId / point

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| requested | `number` |  | 차감 포인트 |
| replacement | `number` |  | 대체 발송 포인트 |
| refund | `number` |  | 환급 포인트 |
| sum | `number` |  | 합계 포인트 |

#### Response / groupList / groupId / app

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| [profit](getmessagegrouplist.md#response-grouplist-groupid-app-profit) | `object` |  | 앱 사용 요금 |
| appId | `string` |  | 앱 아이디 |
| version | `string` |  | 설명 없음 |

#### Response / groupList / groupId / app / profit

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| sms | `number` |  | SMS 사용 요금 |
| lms | `number` |  | LMS 사용 요금 |
| mms | `number` |  | MMS 사용 요금 |
| ata | `number` |  | 알림톡 사용 요금 |
| cta | `number` |  | 친구톡 사용 요금 |

#### Response / groupList / groupId / log

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| message | `object` |  | 로그 메시지 |
| createAt | `date` |  | 로그 기록 일시 |

#### Response / groupList / groupId / countForCharge

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| [sms](getmessagegrouplist.md#response-grouplist-groupid-countforcharge-sms) | `object` |  | SMS 차감 금액 |
| [lms](getmessagegrouplist.md#response-grouplist-groupid-countforcharge-lms) | `object` |  | LMS 차감 금액 |
| [mms](getmessagegrouplist.md#response-grouplist-groupid-countforcharge-mms) | `object` |  | MMS 차감 금액 |
| [ata](getmessagegrouplist.md#response-grouplist-groupid-countforcharge-ata) | `object` |  | 알림톡 차감 금액 |
| [cta](getmessagegrouplist.md#response-grouplist-groupid-countforcharge-cta) | `object` |  | 친구톡 차감 금액 |

#### Response / groupList / groupId / countForCharge / sms

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| country | `number` |  | 국가별 SMS 차감 금액 |

#### Response / groupList / groupId / countForCharge / lms

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| country | `number` |  | 국가별 LMS 차감 금액 |

#### Response / groupList / groupId / countForCharge / mms

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| country | `number` |  | 국가별 MMS 차감 금액 |

#### Response / groupList / groupId / countForCharge / ata

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| country | `number` |  | 국가별 알림톡 차감 금액 |

#### Response / groupList / groupId / countForCharge / cta

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |
| country | `number` |  | 국가별 친구톡 차감 금액 |

#### Response / groupList / groupId / price

| Name | Type | Should Return | Description |
| :--- | :---: | :---: | :--- |


### Samples

#### 그룹목록 조회 startKey 미입력

> **Sample Request**

```text
http://api.solapi.com/messages/v4/groups?limit=10
```

> **Sample Response**

```javascript
{
    "startKey": null,
    "limit": 10,
    "groupList": {
        "G4VZZZZZZZZZZZZZZZZZZZZZZZZZZZZZ": {
            "_id": "G4VZZZZZZZZZZZZZZZZZZZZZZZZZZZZZ",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.229Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4VZZZZZZZZZZZZZZZZZZZZZZZZZZZZZ",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 0
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.240Z",
            "dateUpdated": "2019-08-07T06:59:13.240Z"
        },
        "G4V20190807155913VSSXZSWJLOUNUVX": {
            "_id": "G4V20190807155913VSSXZSWJLOUNUVX",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "countForCharge": {
                "sms": {},
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.951Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "accountId": "12925149",
            "apiVersion": "4",
            "groupId": "G4V20190807155913VSSXZSWJLOUNUVX",
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.953Z",
            "dateUpdated": "2019-08-07T06:59:13.953Z"
        },
        "G4V20190807155913SNJIZNE6QMWIAIW": {
            "_id": "G4V20190807155913SNJIZNE6QMWIAIW",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "countForCharge": {
                "sms": {},
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "message": "유효하지 않은 AppId",
                    "createAt": "2019-08-07T06:59:13.924Z"
                }
            ],
            "status": "FAILED",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "accountId": "12925149",
            "apiVersion": "4",
            "groupId": "G4V20190807155913SNJIZNE6QMWIAIW",
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.934Z",
            "dateUpdated": "2019-08-07T06:59:13.934Z"
        },
        "G4V20190807155913C9KGOEFNL3NON0R": {
            "_id": "G4V20190807155913C9KGOEFNL3NON0R",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "countForCharge": {
                "sms": {},
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": "TESTAPPID",
                "version": null
            },
            "sdkVersion": "1.0",
            "osPlatform": "win",
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.972Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "accountId": "12925149",
            "apiVersion": "4",
            "groupId": "G4V20190807155913C9KGOEFNL3NON0R",
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.980Z",
            "dateUpdated": "2019-08-07T06:59:13.980Z"
        },
        "G4V20190607105937H3PTASXMNJG2JID": {
            "_id": "G4V20190607105937H3PTASXMNJG2JID",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.198Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20190607105937H3PTASXMNJG2JID",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 0
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.200Z",
            "dateUpdated": "2019-08-07T06:59:13.200Z"
        },
        "G4V20190607105937H3PFASXMNJG2JID": {
            "_id": "G4V20190607105937H3PFASXMNJG2JID",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.209Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20190607105937H3PFASXMNJG2JID",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 0
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.225Z",
            "dateUpdated": "2019-08-07T06:59:13.225Z"
        },
        "G4V20180307105937H3PTASXMNJG2JIO": {
            "_id": "G4V20180307105937H3PTASXMNJG2JIO",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 1
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "message": "메시지 그룹이 생성되었습니다.",
                    "createAt": "2019-08-07T06:59:13.052Z"
                },
                {
                    "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.",
                    "createAt": "2019-08-07T06:59:13.052Z"
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20180307105937H3PTASXMNJG2JIO",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 1
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.055Z",
            "dateUpdated": "2019-08-07T06:59:13.055Z"
        },
        "G4V20180307105937H3PTASXMNJG2JID": {
            "_id": "G4V20180307105937H3PTASXMNJG2JID",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:12.946Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20180307105937H3PTASXMNJG2JID",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 0
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:12.967Z",
            "dateUpdated": "2019-08-07T06:59:12.967Z"
        },
        "G4V20180307105937H3PTASXMNJG2JI1": {
            "_id": "G4V20180307105937H3PTASXMNJG2JI1",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 1
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": "PROFITID",
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "message": "메시지 그룹이 생성되었습니다.",
                    "createAt": "2019-08-07T06:59:12.990Z"
                },
                {
                    "message": "국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.",
                    "createAt": "2019-08-07T06:59:12.990Z"
                }
            ],
            "status": "PENDING",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20180307105937H3PTASXMNJG2JI1",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 1
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:12.993Z",
            "dateUpdated": "2019-08-07T06:59:12.993Z"
        },
        "G4V20180307105937CANCELSCHEDULQ5": {
            "_id": "G4V20180307105937CANCELSCHEDULQ5",
            "count": {
                "total": 0,
                "sentTotal": 0,
                "sentFailed": 0,
                "sentSuccess": 0,
                "sentPending": 0,
                "sentReplacement": 0,
                "refund": 0,
                "registeredFailed": 0,
                "registeredSuccess": 0
            },
            "balance": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "point": {
                "requested": 0,
                "replacement": 0,
                "refund": 0,
                "sum": 0
            },
            "app": {
                "profit": {
                    "sms": 0,
                    "lms": 0,
                    "mms": 0,
                    "ata": 0,
                    "cta": 0
                },
                "appId": null,
                "version": null
            },
            "sdkVersion": null,
            "osPlatform": null,
            "log": [
                {
                    "createAt": "2019-08-07T06:59:13.107Z",
                    "message": "메시지 그룹이 생성되었습니다."
                }
            ],
            "status": "SCHEDULED",
            "scheduledDate": null,
            "dateSent": null,
            "dateCompleted": null,
            "isRefunded": false,
            "flagUpdated": false,
            "groupId": "G4V20180307105937CANCELSCHEDULQ5",
            "accountId": "12925149",
            "apiVersion": "4",
            "countForCharge": {
                "sms": {
                    "82": 0
                },
                "lms": {},
                "mms": {},
                "ata": {},
                "cta": {}
            },
            "price": {},
            "dateCreated": "2019-08-07T06:59:13.109Z",
            "dateUpdated": "2019-08-07T06:59:13.109Z"
        }
    },
    "nextKey": "G4V20180307105937CANCELSCHEDULED"
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/messages/v4/groups?limit=10'
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
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  url: 'http://api.solapi.com/messages/v4/groups?limit=10'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/messages/v4/groups?limit=10";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
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

url = "http://api.solapi.com/messages/v4/groups?limit=10"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
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
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    http://api.solapi.com/messages/v4/groups?limit=10
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/groups?limit=10")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
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
  uri := "http://api.solapi.com/messages/v4/groups?limit=10"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")

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
    String targetUrl = "http://api.solapi.com/messages/v4/groups?limit=10";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");

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

