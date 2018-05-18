{% include "../../../fragments/message/delete-reserve-message.md" %}



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
	cancel_opt cancel_info = cancel_opt_init();

	/* set send infomations
	More info found at http://doc.coolsms.co.kr?page_id=1811 */
	// cancel_info.gid = "GID24HL31K4H234";
	cancel_info.mid = "MID52CA262EC49D8";

	result = cancel(&user_info, &cancel_info);
	print_result(result);

	return 0;
}
#endif
```
