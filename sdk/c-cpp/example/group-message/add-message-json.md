{% include "../../../fragments/group-message/add-message-json.md" %}




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
	add_messages_json_opt add_messages_json_info = add_messages_json_opt_init();
	
	add_messages_json_info.group_id = "GID5730430CBE318";
	add_messages_json_info.messages = "[{'type': 'SMS', 'to' : '01000000000,01011111111,01022222222',
            'from' : '01000000000',	'text' : 'Hello A'}, {'type': 'LMS', 'to' : '01033333333', 'from' : 
            '01000000000', 'text' : 'Hello B', 'subject' : 'LMS Subject'}, {'type': 'MMS', 'to' : '01044444444,
             01055555555', 'from' : '01000000000', 'text' : 'Hello C', 'subject' : 'MMS Subject', 'image_id' : 
            'IMG234LSFN234OQ'}]";

	result = add_messages_json(&user_info, &add_messages_json_info);
	print_result(result);

	return 0;
}
#endif
```
