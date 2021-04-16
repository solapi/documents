---
order:
  - createMessageGroup.md
  - addGroupMessages.md
  - getGroupMessageList.md
  - deleteGroupMessages.md
  - sendGroupMessage.md
  - getMessageGroupList.md
  - getMessageGroupInfo.md
  - deleteMessageGroup.md
  - getGroupListExcel.md: false
  - resendGroupMessage.md: false
---

# 그룹 메시지

## 개요

그룹메시지는 대량메시지 뿐만 아니라 소량의 메시지도 안전하게 발송할 수 있는 메커니즘을 제공합니다.

## 기존 API의 문제점

대량의 메시지를 발송 요청하는 프로그램 내에서 루프를 돌며 서버에 발송 요청을 합니다. 이 과정에서 프로그램의 오류 혹은 일시적인 네트워크 오류로 메시지의 누락이 발생할 수 있습니다.

## 그룹메시지의 개선된 기능

일반적으로 아래의 단계를 거치면서 안전하게 발송 할 수 있습니다. : 그룹생성 &gt; 메시지추가 &gt; 리뷰 &gt; 발송

그룹생성 단계에서는 메시지를 담을 바구니를 하나 생성한다고 생각하시면 됩니다.

그 바구니\(그룹\)에 메시지를 추가하고 제대로 담겼는지 확인\(리뷰\) 후 발송하는 순서입니다. 발송 단계에서는 발송 스위치만 켜는 역할로 이미 발송하려는 메시지 내용이 모두 서버에 전송되고 리뷰가 완료된 상태입니다.

