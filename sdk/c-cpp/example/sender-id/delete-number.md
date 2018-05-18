{% include "../../../fragments/sender-id/delete-number.md" %}





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
	delete_opt delete_info = delete_opt_init();

	delete_info.handle_key = "SID573E72B707688";

	result = delete_sender(&user_info, &delete_info);
	print_result(result);

	return 0;
}
#endif
```
