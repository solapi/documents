messages
  : Array 형식의 메시지 발송 정보
  : to
    : 발송하려는 수신번호를 입력합니다. 수신번호는 대시(-) 등 기호를 제외한 번호만 입력합니다. 세 개의 서브파라메터 recipient , recipients , recipientsWithCustomFields 를 통틀어 1개 이상의 >수신번호가 입력되어야 합니다. 한번 요청에 수신번호는 1,000 개를 넘을 수 없습니다.
    : recipient
      : 하나의 수신번호를 입력합니다.
    : recipients
      : 배열 형식의 수신번호 목록을 입력합니다.
    : recipientsWithCustomFields
      : recipient
        : 하나의 수신번호를 입력합니다.
      : customFields
        : 사용자정의 필드를 개수 제한없이 총 160 자까지 입력할 수 있습니다. 요청에 대한 응답에 그대로 리턴되며 발송 이후 메시지로그에서도 조회 가능합니다.
  : from
    : 보내는 사람의 전화번호인 [발신번호](#) 로 보통 고객센터의 전화번호를 사용하며 사전에 등록되어 있어야 합니다.
  : text
    : 메시지 내용
