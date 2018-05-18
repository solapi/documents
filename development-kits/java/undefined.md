# 시작하기

Coolsms JAVA SDK 입니다. SDK를 사용하면 문자전송, 전송내역관리, 알림톡전송 등을 포함하는 여러 Coolsms 서비스를 위한 Java API가 제공되므로 복잡하게 코드를 작성하지 않아도 됩니다.

JDK 1.8 이상의 사용을 권장하며 다운로드 가능한 단일 패키지에는 Coolsms Java 라이브러리, 코드 샘플이 포함되어 있습니다.

## Step 1. Download SDK

아래 방법중 한 가지를 선택해 다운로드 해주세요.

* Maven을 이용해 다운로드 가능합니다. Maven Project에 해당 depoendency를 추가해주세요.

  ```markup
  <dependency>
    <groupId>net.nurigo</groupId>
    <artifactId>javaSDK</artifactId>
    <version>2.2</version>
  </dependency>
  ```

* Coolsms 사이트에서도 다운로드 받으실 수 있습니다. 해당 압축파일에는 Coolsms JAVA SDK 라이브러리, 코드 샘플이 포함되어 있습니다. -&gt; [바로가기](https://www.coolsms.co.kr/index.php?mid=download&document_srl=559455)
* Github를 통해 소스를 가져올 수 있습니다. -&gt; [바로가기](https://github.com/coolsms/java-sdk/releases)

## Step 4. 문자보내기

* 이제 JAVA SDK를 사용할 준비가 되었습니다! [Example](undefined-1/)을 통해 사용 방법을 알아보세요.

### 참고사항

10월 16일 이후로 발신번호 사전등록제로 인해 등록된 발신번호로만 문자를 보내실 수 있습니다. 아래 관련링크를 참고 해주세요.

* [발신번호 사전등록제 공지사항](https://www.coolsms.co.kr/index.php?mid=notice&document_srl=3070386)
* [JAVA SDK 발신번호 등록 방법](undefined-1/undefined-3/)
* [웹 에서 발신번호 등록하기](https://www.coolsms.co.kr/index.php?mid=service_setup&act=dispSmsconfigSenderNumbers)

