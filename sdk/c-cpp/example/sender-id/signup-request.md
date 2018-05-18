{% include "../../../fragments/sender-id/signup-request.md" %}





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
	register_opt register_info = register_opt_init();

	register_info.phone = "01000000000";
	register_info.site_user = "__private__";

	result = register_sender(&user_info, ®ister_info);
	print_result(result);

	return 0;
}
#endif
```
