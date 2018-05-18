## Modules

<dl>
<dt><a href="#module_coolsms-sdk">coolsms-sdk</a></dt>
<dd><p>Coolsms SDK for Javascript</p>
</dd>
<dt><a href="#module_Account">Account</a></dt>
<dd><p>계정정보를 조회합니다. 현재는 잔액정보만 가져올 수 있습니다.</p>
</dd>
<dt><a href="#module_GroupMessage">GroupMessage</a></dt>
<dd><p>그룹메시지 발송을 위해 그룹생성, 삭제, 정보보기, 목록보기 등의 API를 제공합니다.</p>
</dd>
<dt><a href="#module_Images">Images</a></dt>
<dd><p>이미지를 등록, 조회, 삭제합니다.</p>
</dd>
<dt><a href="#module_MessageLog">MessageLog</a></dt>
<dd><p>메시지로그를 조회합니다.</p>
</dd>
<dt><a href="#module_RequestApi">RequestApi</a></dt>
<dd><p>주어진 URL 로 요청하는 모듈입니다. 무조건 POST로 던집니다.</p>
</dd>
<dt><a href="#module_ScheduledMessage">ScheduledMessage</a></dt>
<dd><p>예약된 메시지를 관리합니다.</p>
</dd>
<dt><a href="#module_SimpleMessage">SimpleMessage</a></dt>
<dd><p>한번의 요청으로 메시지를 발송합니다.</p>
</dd>
</dl>

<a id="module_coolsms-sdk"></a>
## coolsms-sdk
Coolsms SDK for Javascript


* [coolsms-sdk](#module_coolsms-sdk)
    * [.SimpleMessage()](#module_coolsms-sdk.SimpleMessage) ⇒ <code>SimpleMessage</code>
    * [.GroupMessage()](#module_coolsms-sdk.GroupMessage) ⇒ <code>GroupMessage</code>
    * [.Account()](#module_coolsms-sdk.Account) ⇒ <code>Account</code>
    * [.MessageLog()](#module_coolsms-sdk.MessageLog) ⇒ <code>MessageLog</code>
    * [.Images()](#module_coolsms-sdk.Images) ⇒ <code>Images</code>
    * [.ScheduledMessage()](#module_coolsms-sdk.ScheduledMessage)

<a id="module_coolsms-sdk.SimpleMessage"></a>
### coolsms-sdk.SimpleMessage() ⇒ <code>SimpleMessage</code>
심플메시지 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
**Returns**: <code>SimpleMessage</code> - 심플메시지 모듈
<a id="module_coolsms-sdk.GroupMessage"></a>
### coolsms-sdk.GroupMessage() ⇒ <code>GroupMessage</code>
그룹메시지 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
**Returns**: <code>GroupMessage</code> - 그룹메시지 모듈
<a id="module_coolsms-sdk.Account"></a>
### coolsms-sdk.Account() ⇒ <code>Account</code>
회원정보 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
**Returns**: <code>Account</code> - 회원정보 모듈
<a id="module_coolsms-sdk.MessageLog"></a>
### coolsms-sdk.MessageLog() ⇒ <code>MessageLog</code>
메시지로그 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
**Returns**: <code>MessageLog</code> - 메시지로그 모듈
<a id="module_coolsms-sdk.Images"></a>
### coolsms-sdk.Images() ⇒ <code>Images</code>
이미지관리 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
**Returns**: <code>Images</code> - 이미지관리 모듈
<a id="module_coolsms-sdk.ScheduledMessage"></a>
### coolsms-sdk.ScheduledMessage()
예약메시지관리 모듈을 리턴합니다.

**Kind**: static method of [<code>coolsms-sdk</code>](#module_coolsms-sdk)
<a id="module_Account"></a>
## Account
계정정보를 조회합니다. 현재는 잔액정보만 가져올 수 있습니다.


* [Account](#module_Account)
    * _static_
        * [.setCredential(apiKey, apiSecret)](#module_Account.setCredential)
        * [.getBalance(callback)](#module_Account.getBalance)
    * _inner_
        * [~getBalanceCallback](#module_Account..getBalanceCallback) : <code>function</code>

<a id="module_Account.setCredential"></a>
### Account.setCredential(apiKey, apiSecret)
API Key 와 API Secret 을 설정한다.

**Kind**: static method of [<code>Account</code>](#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | API Key 입력 |
| apiSecret | <code>string</code> | API Secret 입력 |

<a id="module_Account.getBalance"></a>
### Account.getBalance(callback)
잔액정보를 가져옵니다.

**Kind**: static method of [<code>Account</code>](#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| callback | <code>getBalanceCallback</code> | 잔액정보를 가져온 뒤 호출되는 콜백 함수 |

<a id="module_Account..getBalanceCallback"></a>
### Account~getBalanceCallback : <code>function</code>
잔액정보를 가져온 뒤 호출되는 콜백 함수

**Kind**: inner typedef of [<code>Account</code>](#module_Account)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류 메시지 |
| result | <code>object</code> | 잔액정보를 담은 오브젝트 |

<a id="module_GroupMessage"></a>
## GroupMessage
그룹메시지 발송을 위해 그룹생성, 삭제, 정보보기, 목록보기 등의 API를 제공합니다.


* [GroupMessage](#module_GroupMessage)
    * _static_
        * [.setCredential](#module_GroupMessage.setCredential)
        * [.setDomainName(domainName)](#module_GroupMessage.setDomainName)
        * [.createGroup(groupOptions, callback)](#module_GroupMessage.createGroup)
        * [.addMessages(groupId, messages)](#module_GroupMessage.addMessages)
        * [.deleteMessages(groupId, messages, callback)](#module_GroupMessage.deleteMessages)
        * [.getGroupInfo(groupId, callback)](#module_GroupMessage.getGroupInfo)
        * [.getMessageList(groupId, callback)](#module_GroupMessage.getMessageList)
        * [.getGroupList(callback)](#module_GroupMessage.getGroupList)
        * [.deleteGroups(groups, callback)](#module_GroupMessage.deleteGroups)
        * [.sendMessages(groupId, callback)](#module_GroupMessage.sendMessages)
    * _inner_
        * [~createGroupCallback](#module_GroupMessage..createGroupCallback) : <code>function</code>
        * [~addMessagesCallback](#module_GroupMessage..addMessagesCallback) : <code>function</code>
        * [~deleteMessagesCallback](#module_GroupMessage..deleteMessagesCallback) : <code>function</code>
        * [~getGroupInfoCallback](#module_GroupMessage..getGroupInfoCallback) : <code>function</code>
        * [~deleteGroupsCallback](#module_GroupMessage..deleteGroupsCallback) : <code>function</code>
        * [~sendMessagesCallback](#module_GroupMessage..sendMessagesCallback) : <code>function</code>

<a id="module_GroupMessage.setCredential"></a>
### GroupMessage.setCredential
API Key 및 API Secret 을 설정합니다.

**Kind**: static property of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | API Key 입력 |
| apiSecret | <code>string</code> | API Secret 입력 |

<a id="module_GroupMessage.setDomainName"></a>
### GroupMessage.setDomainName(domainName)
도메인이름을 설정합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| domainName | <code>string</code> | 변경할 도메인이름 (default: https://solapi.com) |

<a id="module_GroupMessage.createGroup"></a>
### GroupMessage.createGroup(groupOptions, callback)
그룹을 생성합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupOptions | <code>object</code> | 그룹 옵션을 입력합니다. |
| callback | <code>createGroupCallback</code> | 그룹 생성 후 호출되는 콜백 함수 |

<a id="module_GroupMessage.addMessages"></a>
### GroupMessage.addMessages(groupId, messages)
그룹에 메시지를 추가합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | <code>string</code> | 메시지를 추가할 그룹아이디 |
| messages | <code>array</code> | 추가할 메시지의 목록 |

<a id="module_GroupMessage.deleteMessages"></a>
### GroupMessage.deleteMessages(groupId, messages, callback)
그룹메시지를 삭제합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | <code>string</code> | 메시지를 삭제할 그룹아이디 |
| messages | <code>array</code> | 삭제할 메시지의 목록 |
| callback | <code>deleteMessagesCallback</code> | 메시지 삭제 후 결과를 받는 콜백 함수 |

<a id="module_GroupMessage.getGroupInfo"></a>
### GroupMessage.getGroupInfo(groupId, callback)
그룹정보 가져오기

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | <code>string</code> | 그룹정보를 가져올 그룹의 아이디 |
| callback | <code>getGroupInfoCallback</code> | 그룹정보를 넘겨받을 콜백 함수 |

<a id="module_GroupMessage.getMessageList"></a>
### GroupMessage.getMessageList(groupId, callback)
그룹메시지 목록을 가져옵니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | <code>string</code> | 그룹메시지 목록을 가져올 그룹아이디 |
| callback | <code>getMessageListCallback</code> | 그룹메시지 목록을 넘겨받을 콜백 함수 |

<a id="module_GroupMessage.getGroupList"></a>
### GroupMessage.getGroupList(callback)
그룹목록을 가져옵니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| callback | <code>getGroupListCallback</code> | 그룹목록을 넘겨받을 콜백 함수 |

<a id="module_GroupMessage.deleteGroups"></a>
### GroupMessage.deleteGroups(groups, callback)
그룹을 삭제합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groups | <code>array</code> | 삭제할 그룹의 목록 |
| callback | <code>deleteGroupsCallback</code> | 삭제 결과를 넘겨받을 콜백 함수 |

<a id="module_GroupMessage.sendMessages"></a>
### GroupMessage.sendMessages(groupId, callback)
그룹메시지를 발송합니다.

**Kind**: static method of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| groupId | <code>string</code> | 발송할 그룹의 아이디 |
| callback | <code>sendMessagesCallback</code> | 발송 후 결과를 리턴받는 콜백 함수 |

<a id="module_GroupMessage..createGroupCallback"></a>
### GroupMessage~createGroupCallback : <code>function</code>
그룹 생성 후 호출되는 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/create-group.html#response-syntax) |

<a id="module_GroupMessage..addMessagesCallback"></a>
### GroupMessage~addMessagesCallback : <code>function</code>
메시지 추가 후 결과를 받는 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/add-messages.html#response-syntax) |

<a id="module_GroupMessage..deleteMessagesCallback"></a>
### GroupMessage~deleteMessagesCallback : <code>function</code>
메시지 삭제 후 결과를 받는 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/delete-messages.html#response-syntax) |

<a id="module_GroupMessage..getGroupInfoCallback"></a>
### GroupMessage~getGroupInfoCallback : <code>function</code>
그룹정보를 넘겨받을 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/get-group-info.html#response-syntax) |

<a id="module_GroupMessage..deleteGroupsCallback"></a>
### GroupMessage~deleteGroupsCallback : <code>function</code>
삭제 결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/delete-groups.html#response-syntax) |

<a id="module_GroupMessage..sendMessagesCallback"></a>
### GroupMessage~sendMessagesCallback : <code>function</code>
발송 후 결과를 리턴받는 콜백 함수

**Kind**: inner typedef of [<code>GroupMessage</code>](#module_GroupMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/group-message/send-messages.html#response-syntax) |

<a id="module_Images"></a>
## Images
이미지를 등록, 조회, 삭제합니다.


* [Images](#module_Images)
    * _static_
        * [.setCredential](#module_Images.setCredential)
        * [.uploadImage(imagePath, callback)](#module_Images.uploadImage)
        * [.getImageList(callback)](#module_Images.getImageList)
        * [.getImageInfo(imageId, callback)](#module_Images.getImageInfo)
        * [.deleteImages(images, callback)](#module_Images.deleteImages)
    * _inner_
        * [~uploadImageCallback](#module_Images..uploadImageCallback) : <code>function</code>
        * [~getImageInfoCallback](#module_Images..getImageInfoCallback) : <code>function</code>
        * [~deleteImagesCallback](#module_Images..deleteImagesCallback) : <code>function</code>

<a id="module_Images.setCredential"></a>
### Images.setCredential
API Key 및 API Secret 설정

**Kind**: static property of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| API | <code>string</code> | Key 입력 |
| API | <code>string</code> | Secret 입력 |

<a id="module_Images.uploadImage"></a>
### Images.uploadImage(imagePath, callback)
이미지 업로드

**Kind**: static method of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| imagePath | <code>string</code> | 업로드 하려는 이미지의 경로 |
| callback | <code>uploadImageCallback</code> | Callback 함수 |

<a id="module_Images.getImageList"></a>
### Images.getImageList(callback)
이미지 목록을 리턴합니다.

**Kind**: static method of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| callback | <code>getImageListCallback</code> | 이미지 목록을 넘겨받는 콜백 함수 |

<a id="module_Images.getImageInfo"></a>
### Images.getImageInfo(imageId, callback)
이미지 정보를 리턴합니다.

**Kind**: static method of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| imageId | <code>string</code> | 이미지 아이디 |
| callback | <code>getImageInfoCallback</code> | 이미지 정보를 넘겨받는 콜백 함수 |

<a id="module_Images.deleteImages"></a>
### Images.deleteImages(images, callback)
이미지를 삭제합니다.

**Kind**: static method of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| images | <code>array</code> | 삭제할 이미지 목록 [Syntax](https://docs.coolsms.co.kr/rest/images/deleteImages.html#request-syntax) |
| callback | <code>deleteImagesCallback</code> | 삭제 결과를 넘겨받는 콜백 함수 |

<a id="module_Images..uploadImageCallback"></a>
### Images~uploadImageCallback : <code>function</code>
이미지 업로드 결과를 넘겨받는 콜백 함수

**Kind**: inner typedef of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/images/uploadImage.html#response-syntax) |

<a id="module_Images..getImageInfoCallback"></a>
### Images~getImageInfoCallback : <code>function</code>
이미지 정보를 넘겨받는 콜백 함수

**Kind**: inner typedef of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류 메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/images/getImageInfo.html#response-syntax) |

<a id="module_Images..deleteImagesCallback"></a>
### Images~deleteImagesCallback : <code>function</code>
삭제 결과를 넘겨받는 콜백 함수

**Kind**: inner typedef of [<code>Images</code>](#module_Images)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류 메시지 |
| result | <code>object</code> | [호출 결과](https://docs.coolsms.co.kr/rest/images/deleteImages.html#response-syntax) |

<a id="module_MessageLog"></a>
## MessageLog
메시지로그를 조회합니다.


* [MessageLog](#module_MessageLog)
    * _static_
        * [.setCredential](#module_MessageLog.setCredential)
        * [.getSentMessages(조회)](#module_MessageLog.getSentMessages)
    * _inner_
        * [~getSentMessagesCallback](#module_MessageLog..getSentMessagesCallback) : <code>function</code>

<a id="module_MessageLog.setCredential"></a>
### MessageLog.setCredential
API Key 및 API Secret 설정

**Kind**: static property of [<code>MessageLog</code>](#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | API Key 입력 |
| apiSecret | <code>string</code> | API Secret 입력 |

<a id="module_MessageLog.getSentMessages"></a>
### MessageLog.getSentMessages(조회)
발송된 메시지를 조회합니다.

**Kind**: static method of [<code>MessageLog</code>](#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| 조회 | <code>object</code> | 옵션 [Syntax](https://docs.coolsms.co.kr/rest/getMessageLogList.html#request-syntax) |

<a id="module_MessageLog..getSentMessagesCallback"></a>
### MessageLog~getSentMessagesCallback : <code>function</code>
조회된 메시지 정보를 넘겨받을 콜백 함수

**Kind**: inner typedef of [<code>MessageLog</code>](#module_MessageLog)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | 요청 결과(https://docs.coolsms.co.kr/rest/getMessageLogList.html#response-syntax) |

<a id="module_RequestApi"></a>
## RequestApi
주어진 URL 로 요청하는 모듈입니다. 무조건 POST로 던집니다.


* [RequestApi](#module_RequestApi)
    * _static_
        * [.request(url, parameters, callback)](#module_RequestApi.request)
        * [.setCredential(apiKey, apiSecret)](#module_RequestApi.setCredential)
    * _inner_
        * [~requestApiCallback](#module_RequestApi..requestApiCallback) : <code>function</code>

<a id="module_RequestApi.request"></a>
### RequestApi.request(url, parameters, callback)
주어진 URL 로 POST 를 던집니다.

**Kind**: static method of [<code>RequestApi</code>](#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| url | <code>string</code> | URL 입력 |
| parameters | <code>object</code> | REQUEST 의 파라메터 |
| callback | <code>requestApi~requestApiCallback</code> | 콜백 함수 |

<a id="module_RequestApi.setCredential"></a>
### RequestApi.setCredential(apiKey, apiSecret)
Set api public and secret keys

**Kind**: static method of [<code>RequestApi</code>](#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | api public key |
| apiSecret | <code>string</code> | api secret key |

<a id="module_RequestApi..requestApiCallback"></a>
### RequestApi~requestApiCallback : <code>function</code>
요청 후 결과 받는 콜백 함수

**Kind**: inner typedef of [<code>RequestApi</code>](#module_RequestApi)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류 메시지 |
| result | <code>object</code> | 요청 결과 |

<a id="module_ScheduledMessage"></a>
## ScheduledMessage
예약된 메시지를 관리합니다.


* [ScheduledMessage](#module_ScheduledMessage)
    * _static_
        * [.setCredential](#module_ScheduledMessage.setCredential)
        * [.getScheduledMessages(callback)](#module_ScheduledMessage.getScheduledMessages)
        * [.cancelScheduledMessages(messages, callback)](#module_ScheduledMessage.cancelScheduledMessages)
    * _inner_
        * [~getScheduledMessagesCallback](#module_ScheduledMessage..getScheduledMessagesCallback) : <code>function</code>
        * [~cancelScheduledMessagesCallback](#module_ScheduledMessage..cancelScheduledMessagesCallback) : <code>function</code>

<a id="module_ScheduledMessage.setCredential"></a>
### ScheduledMessage.setCredential
API Key 및 API Secret 설정

**Kind**: static property of [<code>ScheduledMessage</code>](#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | API Key 입력 |
| apiSecret | <code>string</code> | API Secret 입력 |

<a id="module_ScheduledMessage.getScheduledMessages"></a>
### ScheduledMessage.getScheduledMessages(callback)
예약된 메시지 조회

**Kind**: static method of [<code>ScheduledMessage</code>](#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| callback | <code>getScheduledMessagesCallback</code> | 조회결과를 넘겨받을 콜백 함수 |

<a id="module_ScheduledMessage.cancelScheduledMessages"></a>
### ScheduledMessage.cancelScheduledMessages(messages, callback)
예약메시지를 취소합니다.

**Kind**: static method of [<code>ScheduledMessage</code>](#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| messages | <code>array</code> | 취소할 예약메시지 목록 [Syntax](https://docs.coolsms.co.kr/rest/scheduled-message/cancelScheduledMessages.html#request-syntax) |
| callback | <code>cancelScheduledMessagesCallback</code> | 취소 결과를 넘겨받을 콜백 함수 |

<a id="module_ScheduledMessage..getScheduledMessagesCallback"></a>
### ScheduledMessage~getScheduledMessagesCallback : <code>function</code>
조회결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [<code>ScheduledMessage</code>](#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [요청 결과](https://docs.coolsms.co.kr/rest/scheduled-message/getScheduledMessages.html#response-syntax) |

<a id="module_ScheduledMessage..cancelScheduledMessagesCallback"></a>
### ScheduledMessage~cancelScheduledMessagesCallback : <code>function</code>
취소 결과를 넘겨받을 콜백 함수

**Kind**: inner typedef of [<code>ScheduledMessage</code>](#module_ScheduledMessage)

| Param | Type | Description |
| --- | --- | --- |
| error | <code>string</code> | 오류메시지 |
| result | <code>object</code> | [요청 결과](https://docs.coolsms.co.kr/rest/scheduled-message/cancelScheduledMessages.html#response-syntax) |

<a id="module_SimpleMessage"></a>
## SimpleMessage
한번의 요청으로 메시지를 발송합니다.


* [SimpleMessage](#module_SimpleMessage)
    * [.setCredential](#module_SimpleMessage.setCredential)
    * [.sendMessages(params)](#module_SimpleMessage.sendMessages)

<a id="module_SimpleMessage.setCredential"></a>
### SimpleMessage.setCredential
API Key 및 API Secret 설정

**Kind**: static property of [<code>SimpleMessage</code>](#module_SimpleMessage)

| Param | Type | Description |
| --- | --- | --- |
| apiKey | <code>string</code> | API Key 입력 |
| apiSecret | <code>string</code> | API Secret 입력 |

<a id="module_SimpleMessage.sendMessages"></a>
### SimpleMessage.sendMessages(params)
한번의 요청으로 메시지를 발송합니다.

**Kind**: static method of [<code>SimpleMessage</code>](#module_SimpleMessage)

| Param | Type | Description |
| --- | --- | --- |
| params | <code>object</code> | 발송할 메시지 데이터 [Syntax](https://docs.coolsms.co.kr/rest/simple-message.html#request-syntax) |
