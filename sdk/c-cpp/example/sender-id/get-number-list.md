{% include "../../../fragments/sender-id/get-number-list.md" %}




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
	list_opt list_info = list_opt_init();

	list_info.site_user = "__private__";

	result = list(&user_info, &list_info);
	print_result(result);

	return 0;
}
#endif
```
