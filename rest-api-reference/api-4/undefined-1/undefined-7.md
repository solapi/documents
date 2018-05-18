# 그룹 메시지 삭제

## 그룹 메시지 삭제

그룹에 추가된 문자메시지를 삭제합니다.

### Request

DELETE [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages](https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages)

curl -X DELETE [https://rest.coolsms.co.kr/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages](https://rest.coolsms.co.kr/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"  -d '{"messageIds":\["M4V20180308120044DTYYJBBYLPQZIB1", "M4V20180309120044DTYYJBBYLPQZIB1"\]}'

#### Required Path Parameters

* `groupId` - 삭제할 메시지가 있는 그룹의 아이디

#### Required Body Parameters

* `messageIds` - 배열 형태인 삭제할 메시지의 아이디들

#### Sample Code

request\( { url: "[https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO/messages](https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO/messages)", method: 'delete', headers: { 'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]` }, json: { messageIds: \[ 'M4V20180308120044DTYYJBBYLPQZIB1', 'M4V20180309120044DTYYJBBYLPQZIB1' \] } } \)

conn = HTTPSConnection\('rest.coolsms.co.kr'\) conn.request\( "DELETE", "/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO/messages","{messageIds:\['M4V20180308120044DTYYJBBYLPQZIB1', 'M4V20180309120044DTYYJBBYLPQZIB1'\]}", {"Authorization":"HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"}\) conn.close\(\)

&lt;?php $ch = curl\_init\(\); curl\_setopt\($ch, CURLOPT\_URL, "[https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO/messages](https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO/messages)"\); curl\_setopt\($ch, CURLOPT\_CUSTOMREQUEST, "DELETE"\); curl\_setopt\($ch, CURLOPT\_POSTFIELDS, "{'messageIds':\['M4V20180308120044DTYYJBBYLPQZIB1', 'M4V20180309120044DTYYJBBYLPQZIB1'\]}"\); curl\_setopt\($ch, CURLOPT\_HTTPHEADER, array\( 'Authorization: HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]' \)\); curl\_exec\($ch\); curl\_close\($ch\);

### Response

{ "errorCount": Number, "resultList": \[ { "messageId": "String", "resultCode": "String" } \] }

{ "errorCount": 0, "resultList": \[ { "messageId": "MID1234567890", "resultCode": "Success" } \] }

* `errorCount` - 오류 카운트
* `resultList` - 요청한 건수만큼 결과를 반환합니다. 
  * `messageId` - 삭제하려는 메시지의 아이디
  * `resultCode` - 삭제 성공 여부 \(Success, MessageNotFound, InternalError\)

## Errors

* `Unauthorized(401)` - 권한 오류

