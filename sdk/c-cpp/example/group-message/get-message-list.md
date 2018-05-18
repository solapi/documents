{% include "../../../fragments/group-message/get-message-list.md" %}




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
	message_list_opt message_list_info = message_list_opt_init();

	message_list_info.group_id = "GID573D2CD5BDFED";
	message_list_info.offset = "0";
	message_list_info.limit = "20";

	result = get_message_list(&user_info, &message_list_info);
	print_result(result);

	return 0;
}
#endif
```