{% include "../../../fragments/message/sms.md" %}




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
	send_opt send_info = send_opt_init();
	
	send_info.to = "01000000000";
	send_info.from = "01000000000";
	send_info.text = "SMS 문자 테스트입니다.";
	// send_info.type = "SMS";

	result = send_message(&user_info, &send_info);
	print_result(result);

	return 0;
}
#endif
```