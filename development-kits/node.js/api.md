# API 레퍼런스

## Modules

[coolsms-sdk](api.md#module_coolsms-sdk)

Coolsms SDK for Javascript[Account](api.md#module_Account)

계정정보를 조회합니다. 현재는 잔액정보만 가져올 수 있습니다.[GroupMessage](api.md#module_GroupMessage)

그룹메시지 발송을 위해 그룹생성, 삭제, 정보보기, 목록보기 등의 API를 제공합니다.[Images](api.md#module_Images)

이미지를 등록, 조회, 삭제합니다.[MessageLog](api.md#module_MessageLog)

메시지로그를 조회합니다.[RequestApi](api.md#module_RequestApi)

주어진 URL 로 요청하는 모듈입니다. 무조건 POST로 던집니다.[ScheduledMessage](api.md#module_ScheduledMessage)

예약된 메시지를 관리합니다.[SimpleMessage](api.md#module_SimpleMessage)

한번의 요청으로 메시지를 발송합니다.

## coolsms-sdk

Coolsms SDK for Javascript

* [coolsms-sdk](api.md#module_coolsms-sdk)
  * [.SimpleMessage\(\)](api.md#module_coolsms-sdk.SimpleMessage) ⇒ `SimpleMessage`
  * [.GroupMessage\(\)](api.md#module_coolsms-sdk.GroupMessage) ⇒ `GroupMessage`
  * [.Account\(\)](api.md#module_coolsms-sdk.Account) ⇒ `Account`
  * [.MessageLog\(\)](api.md#module_coolsms-sdk.MessageLog) ⇒ `MessageLog`
  * [.Images\(\)](api.md#module_coolsms-sdk.Images) ⇒ `Images`
  * [.ScheduledMessage\(\)](api.md#module_coolsms-sdk.ScheduledMessage)

### coolsms-sdk.SimpleMessage\(\) ⇒ `SimpleMessage`

심플메시지 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) **Returns**: `SimpleMessage` - 심플메시지 모듈 

### coolsms-sdk.GroupMessage\(\) ⇒ `GroupMessage`

그룹메시지 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) **Returns**: `GroupMessage` - 그룹메시지 모듈 

### coolsms-sdk.Account\(\) ⇒ `Account`

회원정보 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) **Returns**: `Account` - 회원정보 모듈 

### coolsms-sdk.MessageLog\(\) ⇒ `MessageLog`

메시지로그 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) **Returns**: `MessageLog` - 메시지로그 모듈 

### coolsms-sdk.Images\(\) ⇒ `Images`

이미지관리 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) **Returns**: `Images` - 이미지관리 모듈 

### coolsms-sdk.ScheduledMessage\(\)

예약메시지관리 모듈을 리턴합니다.

**Kind**: static method of [`coolsms-sdk`](api.md#module_coolsms-sdk) 

## Account

계정정보를 조회합니다. 현재는 잔액정보만 가져올 수 있습니다.

* [Account](api.md#module_Account)
  * _static_
    * [.setCredential\(apiKey, apiSecret\)](api.md#module_Account.setCredential)
    * [.getBalance\(callback\)](api.md#module_Account.getBalance)
  * _inner_
    * [~getBalanceCallback](api.md#module_Account..getBalanceCallback) : `function`

### Account.setCredential\(apiKey, apiSecret\)

API Key 와 API Secret 을 설정한다.

**Kind**: static method of [`Account`](api.md#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | API Key 입력 |
| apiSecret | `string` | API Secret 입력 |

### Account.getBalance\(callback\)

잔액정보를 가져옵니다.

**Kind**: static method of [`Account`](api.md#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| callback | `getBalanceCallback` | 잔액정보를 가져온 뒤 호출되는 콜백 함수 |

### Account~getBalanceCallback : `function`

잔액정보를 가져온 뒤 호출되는 콜백 함수

**Kind**: inner typedef of [`Account`](api.md#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류 메시지 |
| result | `object` | 잔액정보를 담은 오브젝트 |

## GroupMessage

그룹메시지 발송을 위해 그룹생성, 삭제, 정보보기, 목록보기 등의 API를 제공합니다.

* [GroupMessage](api.md#module_GroupMessage)
  * _static_
    * [.setCredential](api.md#module_GroupMessage.setCredential)
    * [.setDomainName\(domainName\)](api.md#module_GroupMessage.setDomainName)
    * [.createGroup\(groupOptions, callback\)](api.md#module_GroupMessage.createGroup)
    * [.addMessages\(groupId, messages\)](api.md#module_GroupMessage.addMessages)
    * [.deleteMessages\(groupId, messages, callback\)](api.md#module_GroupMessage.deleteMessages)
    * [.getGroupInfo\(groupId, callback\)](api.md#module_GroupMessage.getGroupInfo)
    * [.getMessageList\(groupId, callback\)](api.md#module_GroupMessage.getMessageList)
    * [.getGroupList\(callback\)](api.md#module_GroupMessage.getGroupList)
    * [.deleteGroups\(groups, callback\)](api.md#module_GroupMessage.deleteGroups)
    * [.sendMessages\(groupId, callback\)](api.md#module_GroupMessage.sendMessages)
  * _inner_
    * [~createGroupCallback](api.md#module_GroupMessage..createGroupCallback) : `function`
    * [~addMessagesCallback](api.md#module_GroupMessage..addMessagesCallback) : `function`
    * [~deleteMessagesCallback](api.md#module_GroupMessage..deleteMessagesCallback) : `function`
    * [~getGroupInfoCallback](api.md#module_GroupMessage..getGroupInfoCallback) : `function`
    * [~deleteGroupsCallback](api.md#module_GroupMessage..deleteGroupsCallback) : `function`
    * [~sendMessagesCallback](api.md#module_GroupMessage..sendMessagesCallback) : `function`

### GroupMessage.setCredential

API Key 및 API Secret 을 설정합니다.

**Kind**: static property of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | API Key 입력 |
| apiSecret | `string` | API Secret 입력 |

### GroupMessage.setDomainName\(domainName\)

도메인이름을 설정합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| domainName | `string` | 변경할 도메인이름 \(default: [https://solapi.com](https://solapi.com)\) |

### GroupMessage.createGroup\(groupOptions, callback\)

그룹을 생성합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupOptions | `object` | 그룹 옵션을 입력합니다. |
| callback | `createGroupCallback` | 그룹 생성 후 호출되는 콜백 함수 |

### GroupMessage.addMessages\(groupId, messages\)

그룹에 메시지를 추가합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | `string` | 메시지를 추가할 그룹아이디 |
| messages | `array` | 추가할 메시지의 목록 |

### GroupMessage.deleteMessages\(groupId, messages, callback\)

그룹메시지를 삭제합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | `string` | 메시지를 삭제할 그룹아이디 |
| messages | `array` | 삭제할 메시지의 목록 |
| callback | `deleteMessagesCallback` | 메시지 삭제 후 결과를 받는 콜백 함수 |

### GroupMessage.getGroupInfo\(groupId, callback\)

그룹정보 가져오기

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | `string` | 그룹정보를 가져올 그룹의 아이디 |
| callback | `getGroupInfoCallback` | 그룹정보를 넘겨받을 콜백 함수 |

### GroupMessage.getMessageList\(groupId, callback\)

그룹메시지 목록을 가져옵니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | `string` | 그룹메시지 목록을 가져올 그룹아이디 |
| callback | `getMessageListCallback` | 그룹메시지 목록을 넘겨받을 콜백 함수 |

### GroupMessage.getGroupList\(callback\)

그룹목록을 가져옵니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| callback | `getGroupListCallback` | 그룹목록을 넘겨받을 콜백 함수 |

### GroupMessage.deleteGroups\(groups, callback\)

그룹을 삭제합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groups | `array` | 삭제할 그룹의 목록 |
| callback | `deleteGroupsCallback` | 삭제 결과를 넘겨받을 콜백 함수 |

### GroupMessage.sendMessages\(groupId, callback\)

그룹메시지를 발송합니다.

**Kind**: static method of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | `string` | 발송할 그룹의 아이디 |
| callback | `sendMessagesCallback` | 발송 후 결과를 리턴받는 콜백 함수 |

### GroupMessage~createGroupCallback : `function`

그룹 생성 후 호출되는 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/create-group.html#response-syntax) |

### GroupMessage~addMessagesCallback : `function`

메시지 추가 후 결과를 받는 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/add-messages.html#response-syntax) |

### GroupMessage~deleteMessagesCallback : `function`

메시지 삭제 후 결과를 받는 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/delete-messages.html#response-syntax) |

### GroupMessage~getGroupInfoCallback : `function`

그룹정보를 넘겨받을 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/get-group-info.html#response-syntax) |

### GroupMessage~deleteGroupsCallback : `function`

삭제 결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/delete-groups.html#response-syntax) |

### GroupMessage~sendMessagesCallback : `function`

발송 후 결과를 리턴받는 콜백 함수

**Kind**: inner typedef of [`GroupMessage`](api.md#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/send-messages.html#response-syntax) |

## Images

이미지를 등록, 조회, 삭제합니다.

* [Images](api.md#module_Images)
  * _static_
    * [.setCredential](api.md#module_Images.setCredential)
    * [.uploadImage\(imagePath, callback\)](api.md#module_Images.uploadImage)
    * [.getImageList\(callback\)](api.md#module_Images.getImageList)
    * [.getImageInfo\(imageId, callback\)](api.md#module_Images.getImageInfo)
    * [.deleteImages\(images, callback\)](api.md#module_Images.deleteImages)
  * _inner_
    * [~uploadImageCallback](api.md#module_Images..uploadImageCallback) : `function`
    * [~getImageInfoCallback](api.md#module_Images..getImageInfoCallback) : `function`
    * [~deleteImagesCallback](api.md#module_Images..deleteImagesCallback) : `function`

### Images.setCredential

API Key 및 API Secret 설정

**Kind**: static property of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| API | `string` | Key 입력 |
| API | `string` | Secret 입력 |

### Images.uploadImage\(imagePath, callback\)

이미지 업로드

**Kind**: static method of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| imagePath | `string` | 업로드 하려는 이미지의 경로 |
| callback | `uploadImageCallback` | Callback 함수 |

### Images.getImageList\(callback\)

이미지 목록을 리턴합니다.

**Kind**: static method of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| callback | `getImageListCallback` | 이미지 목록을 넘겨받는 콜백 함수 |

### Images.getImageInfo\(imageId, callback\)

이미지 정보를 리턴합니다.

**Kind**: static method of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| imageId | `string` | 이미지 아이디 |
| callback | `getImageInfoCallback` | 이미지 정보를 넘겨받는 콜백 함수 |

### Images.deleteImages\(images, callback\)

이미지를 삭제합니다.

**Kind**: static method of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| images | `array` | 삭제할 이미지 목록 [Syntax](https://docs.coolsms.co.kr/rest/images/deleteImages.html#request-syntax) |
| callback | `deleteImagesCallback` | 삭제 결과를 넘겨받는 콜백 함수 |

### Images~uploadImageCallback : `function`

이미지 업로드 결과를 넘겨받는 콜백 함수

**Kind**: inner typedef of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/images/uploadImage.html#response-syntax) |

### Images~getImageInfoCallback : `function`

이미지 정보를 넘겨받는 콜백 함수

**Kind**: inner typedef of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류 메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/images/getImageInfo.html#response-syntax) |

### Images~deleteImagesCallback : `function`

삭제 결과를 넘겨받는 콜백 함수

**Kind**: inner typedef of [`Images`](api.md#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류 메시지 |
| result | `object` | [호출 결과](https://docs.coolsms.co.kr/rest/images/deleteImages.html#response-syntax) |

## MessageLog

메시지로그를 조회합니다.

* [MessageLog](api.md#module_MessageLog)
  * _static_
    * [.setCredential](api.md#module_MessageLog.setCredential)
    * [.getSentMessages\(조회\)](api.md#module_MessageLog.getSentMessages)
  * _inner_
    * [~getSentMessagesCallback](api.md#module_MessageLog..getSentMessagesCallback) : `function`

### MessageLog.setCredential

API Key 및 API Secret 설정

**Kind**: static property of [`MessageLog`](api.md#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | API Key 입력 |
| apiSecret | `string` | API Secret 입력 |

### MessageLog.getSentMessages\(조회\)

발송된 메시지를 조회합니다.

**Kind**: static method of [`MessageLog`](api.md#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| 조회 | `object` | 옵션 [Syntax](https://docs.coolsms.co.kr/rest/getMessageLogList.html#request-syntax) |

### MessageLog~getSentMessagesCallback : `function`

조회된 메시지 정보를 넘겨받을 콜백 함수

**Kind**: inner typedef of [`MessageLog`](api.md#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | 요청 결과\([https://docs.coolsms.co.kr/rest/getMessageLogList.html\#response-syntax](https://docs.coolsms.co.kr/rest/getMessageLogList.html#response-syntax)\) |

## RequestApi

주어진 URL 로 요청하는 모듈입니다. 무조건 POST로 던집니다.

* [RequestApi](api.md#module_RequestApi)
  * _static_
    * [.request\(url, parameters, callback\)](api.md#module_RequestApi.request)
    * [.setCredential\(apiKey, apiSecret\)](api.md#module_RequestApi.setCredential)
  * _inner_
    * [~requestApiCallback](api.md#module_RequestApi..requestApiCallback) : `function`

### RequestApi.request\(url, parameters, callback\)

주어진 URL 로 POST 를 던집니다.

**Kind**: static method of [`RequestApi`](api.md#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| url | `string` | URL 입력 |
| parameters | `object` | REQUEST 의 파라메터 |
| callback | `requestApi~requestApiCallback` | 콜백 함수 |

### RequestApi.setCredential\(apiKey, apiSecret\)

Set api public and secret keys

**Kind**: static method of [`RequestApi`](api.md#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | api public key |
| apiSecret | `string` | api secret key |

### RequestApi~requestApiCallback : `function`

요청 후 결과 받는 콜백 함수

**Kind**: inner typedef of [`RequestApi`](api.md#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류 메시지 |
| result | `object` | 요청 결과 |

## ScheduledMessage

예약된 메시지를 관리합니다.

* [ScheduledMessage](api.md#module_ScheduledMessage)
  * _static_
    * [.setCredential](api.md#module_ScheduledMessage.setCredential)
    * [.getScheduledMessages\(callback\)](api.md#module_ScheduledMessage.getScheduledMessages)
    * [.cancelScheduledMessages\(messages, callback\)](api.md#module_ScheduledMessage.cancelScheduledMessages)
  * _inner_
    * [~getScheduledMessagesCallback](api.md#module_ScheduledMessage..getScheduledMessagesCallback) : `function`
    * [~cancelScheduledMessagesCallback](api.md#module_ScheduledMessage..cancelScheduledMessagesCallback) : `function`

### ScheduledMessage.setCredential

API Key 및 API Secret 설정

**Kind**: static property of [`ScheduledMessage`](api.md#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | API Key 입력 |
| apiSecret | `string` | API Secret 입력 |

### ScheduledMessage.getScheduledMessages\(callback\)

예약된 메시지 조회

**Kind**: static method of [`ScheduledMessage`](api.md#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| callback | `getScheduledMessagesCallback` | 조회결과를 넘겨받을 콜백 함수 |

### ScheduledMessage.cancelScheduledMessages\(messages, callback\)

예약메시지를 취소합니다.

**Kind**: static method of [`ScheduledMessage`](api.md#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| messages | `array` | 취소할 예약메시지 목록 [Syntax](https://docs.coolsms.co.kr/rest/scheduled-message/cancelScheduledMessages.html#request-syntax) |
| callback | `cancelScheduledMessagesCallback` | 취소 결과를 넘겨받을 콜백 함수 |

### ScheduledMessage~getScheduledMessagesCallback : `function`

조회결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [`ScheduledMessage`](api.md#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [요청 결과](https://docs.coolsms.co.kr/rest/scheduled-message/getScheduledMessages.html#response-syntax) |

### ScheduledMessage~cancelScheduledMessagesCallback : `function`

취소 결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [`ScheduledMessage`](api.md#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | `string` | 오류메시지 |
| result | `object` | [요청 결과](https://docs.coolsms.co.kr/rest/scheduled-message/cancelScheduledMessages.html#response-syntax) |

## SimpleMessage

한번의 요청으로 메시지를 발송합니다.

* [SimpleMessage](api.md#module_SimpleMessage)
  * [.setCredential](api.md#module_SimpleMessage.setCredential)
  * [.sendMessages\(params\)](api.md#module_SimpleMessage.sendMessages)

### SimpleMessage.setCredential

API Key 및 API Secret 설정

**Kind**: static property of [`SimpleMessage`](api.md#module_SimpleMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | `string` | API Key 입력 |
| apiSecret | `string` | API Secret 입력 |

### SimpleMessage.sendMessages\(params\)

한번의 요청으로 메시지를 발송합니다.

**Kind**: static method of [`SimpleMessage`](api.md#module_SimpleMessage)

| Param | Type | Description |
| --- | --- | --- |
| params | `object` | 발송할 메시지 데이터 [Syntax](https://docs.coolsms.co.kr/rest/simple-message.html#request-syntax) |

