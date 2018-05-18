{% include "../../../fragments/group-message/get-group-info.md" %}




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
	group_info_opt group_info_info = group_info_opt_init();

	group_info_info.group_id = "GID573D2C9C8A4CE";

	result = get_group_info(&user_info, &group_info_info);
	print_result(result);

	return 0;
}
#endif
```