messages
  : Array 형식의 메시지 발송 정보
  : type
    : 메시지 유형을 입력합니다.
    : 입력 가능한 값
      : `AUTO` *default*
        : 메시지 내용에 따라 SMS, LMS, MMS 를 발송합니다. 국가번호 82(한국)외 해외문자인 경우 SMS 로 자동변경.
      : `SMS`
        : 영자 90 자(한글 45 자) 이하의 단문메시지를 발송합니다.
      : `LMS`
        : 영자 2,000 자(한글 1,000 자) 이하의 장문메시지를 발송합니다.
      : `MMS`
        : 영자 2,000 자(한글 1,000 자) 이하의 메시지와 1개의 이미지 전송. 이미지는 300KB 이하, 2048x2048픽셀 이하인 JPEG, PNG, GIF 형식의 파일.
      : `ATA`
        : 한/영 포함 1,000 자의 텍스트를 발송할 수 있는 카카오톡의 [알림톡](#)
      : `CTA`
        : 한/영 포함 1,000 자의 텍스트를 보낼 수 있는 카카오톡의 [친구톡](#)
    : 국가번호 82(한국)외 해외문자인 경우 SMS 만 발송가능하고 LMS, MMS 는 발송불가.
  : country
    : 발송하려는 국가의 국가번호를 입력합니다.
    : 입력 가능한 값
      : `82` *default*
        : 한국
      : `81`
        : 일본
      : `86`
        : 중국
      : `886`
        : 대만
      : `1`
        : 미국
      : `기타`
        : 해당 국가의 국제전화 국가코드
        : ***참고***
          : 국제전화 국가코드는 [ITU-T](https://ko.wikipedia.org/wiki/ITU-T) 의 [E.164](https://en.wikipedia.org/wiki/E.164) 에서 지정한 [Country Calling Codes](https://en.wikipedia.org/wiki/List_of_country_calling_codes) 을 참고하세요.
    : 국가번호가 82(한국) 일 때에만 LMS, MMS 발송 가능합니다. 이외 국가에서는 SMS 만 발송 가능합니다.
  : subject
    : type이 LMS, MMS 일 때 제목
  : imageId
    : 이미지 으로 등록할 때 리턴되는 [이미지](#) ID
  : kakaoOptions
    : 카카오톡 메시지 옵션
    : senderKey
      : 알림톡 Sender Key
    : templateCode
      : 알림톡 Template Code
    : buttonName
      : 카카오톡 버튼 이름, 10 자 제한
    : buttonUrl
      : 카카오톡 버튼 URL, 100 자 제한
    : disableSms
      : 알림톡 및 친구톡 발송에 실패하여도 문자메시지로 대체하여 발송하지 않습니다.
      : 입력 가능한 값
        : `true`
          : 알림톡 실패시 문자로 대체하지 않음
        : `false` *default*
          : 알림톡 실패시 문자로 대체 발송
