# 메시지내역 보기

```c
#include "coolsms.h"

/* Set 1 to test example */
#if 0
int main()
{
    /* api_key and api_secret can be obtained from http://www.coolsms.co.kr */
    response_struct result;
    char *api_key = "API_KEY";
    char *api_secret = "API_SECRET";
    user_opt user_info = user_opt_init(api_key, api_secret);
    sent_opt sent_info = sent_opt_init();

    sent_info.offset = "0";                         // 가져올 목록의 시작 위치
    sent_info.limit = "10";                         // 기본값 20, 20개의 목록을 받을 수 있으며 40 입력시 40개의 목록이 리턴
    // sent_info.rcpt = "01000000000";              // 수신번호로 검색
    // sent_info.start = "201603121020";            // 검색 시작일시
    // sent_info.end = "201603121159";              // 검색 종료일시
    // sent_info.status = "00";                     // 메세지 상태 값
    // sent_info.resultcode = "54";                 // 전송결과 값
    // sent_info.notin_resultcode = "00";           // 입력된 전송결과 값 이외의 건
    // sent_info.messate_id = "MID52CA262EC49D8";   // 메세지 ID 값
    // sent_info.group_id = "GID24HL31K4H234";      // 그룹 ID 값

    result = sent(&user_info, &sent_info);
    print_result(result);

    return 0;
}
#endif
```

