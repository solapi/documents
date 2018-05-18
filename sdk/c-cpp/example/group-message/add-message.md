{% include "../../../fragments/group-message/add-message.md" %}




```c
#include "coolsms.h"

/* Set 1 to test example */
#if 0
int main()
{
	/* api_key and api_secret can be obtained from http://www.coolsms.co.kr */
	response_struct result;
	char *api_key = "NCS55F7C0B9269DB";
	char *api_secret = "D2ED4C0E5C55D59F33E74484E89F232B";
	user_opt user_info = user_opt_init(api_key, api_secret);
	add_messages_opt add_messages_info = add_messages_opt_init();

	add_messages_info.group_id = "GID573D2CD5BDFED";
	add_messages_info.to = "01000000000";
	add_messages_info.from = "01000000000";
	add_messages_info.text = "CoolSMS Message Test!";
	// add_messages_info.subject = "";
	add_messages_info.type = "SMS";
	// add_messages_info.image_id = "IMG234LSFN234OQ";
	// add_messages_info.refname = "";
	// add_messages_info.country_code = "82";

	result = add_messages(&user_info, &add_messages_info);
	print_result(result);

	return 0;
}
#endif
```