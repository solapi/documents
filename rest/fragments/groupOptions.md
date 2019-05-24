* `groupOptions` - 그룹 옵션
  * `appId` - 어플리케이션을 구분하는 ID 로 사용되며 솔루션 제공에 대한 수수료 정산의 기준이 되는 ID 이기도 합니다. 자세한 안내는 http://solapi.com/sp 을 참고하세요.
  * `appVersion` - 어플리케이션 버전, 예) Purplebook 4.1
  * `testMode` - 값이 true 이면 CARRIER 시뮬레이터로 시뮬레이션됩니다. 수신번호를 반드시 01000000000 ~ 01000009999 범위 내에서 테스트합니다. 결과값은 60으로 고정됩니다.
  
    입력 가능한 값

    * `false` *default* - 메시지를 실제 발송합니다.
    * `true` - 테스트 모드로 실제 발송하지 않고 내부 시뮬레이션을 타게 합니다.

  * `forceSms` - 누리고푸시를 사용하더라도 푸시로 발송하지 않고 문자메시지로 발송합니다.
   
    입력 가능한 값

    * `true` - 강제 문자 발송
    * `false` *default* - 푸시 발송 실패시 문자 발송

  * `osPlatform` - 클라이언트의 OS 및 플랫폼 버전, 예) CentOS 6.6
  * `devLanguage` - 개발 프로그래밍 언어, 예) PHP 5.3.3
  * `sdkVersion` - SDK 버전, 예) PHP SDK 1.5
  * `scheduledDate` - YYYY-MM-DD HH:MI:SS 포맷의 예약시간.
