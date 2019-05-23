# 그룹메시지

그룹메시지는 대량메시지 뿐만 아니라 소량의 메시지도 안전하게 발송할 수 있는 메커니즘을 제공합니다.

## 기존 API의 문제점

대량의 메시지를 발송 요청하는 프로그램 내에서 루프를 돌며 서버에 발송 요청을 합니다.

이 과정에서 프로그램의 오류 혹은 일시적인 네트워크 오류로 메시지의 누락이 발생할 수 있습니다.

## 쿨에스엠에스 그룹메시지의 개선된 기능

일반적으로 아래의 단계를 거치면서 안전하게 발송 할 수 있습니다. : 그룹생성 &gt; 메시지추가 &gt; 리뷰 &gt; 발송

그룹생성 단계에서는 메시지를 담을 바구니를 하나 생성한다고 생각하시면 됩니다.

그 바구니\(그룹\)에 메시지를 추가하고 제대로 담겼는지 확인\(리뷰\) 후 발송하는 순서입니다. 발송 단계에서는 발송 스위치만 켜는 역할로 이미 발송하려는 메시지 내용이 모두 서버에 전송되고 리뷰가 완료된 상태입니다.

* [그룹 생성](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/1.%20createGroup.md)
* [그룹 목록](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/2.%20getGroupList.md)
* [그룹 정보](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/3.%20getGroupInfo.md)
* [그룹 삭제](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/4.%20deleteGroups.md)
* [그룹 메시지 추가](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/5.%20addGroupMessages.md)
* [그룹 메시지 목록](https://docs.solapi.com/rest-api-reference/api-4/group/list) 
* [그룹 메시지 발송](https://docs.solapi.com/rest-api-reference/api-4/group/send)
* [그룹 메시지 삭제](https://github.com/solapi/documents/tree/3e25e2f0ec550ab91a6b2f5e2f285464dc36e170/3.%20ms/4.%20messages-v4/2.%20group-message/8.%20deleteGroupMessages.md)

