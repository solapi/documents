# 메시지 삭제

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
    delete_messages_opt delete_messages_info = delete_messages_opt_init();

    delete_messages_info.group_id = "GID573D2CD5BDFED";
    delete_messages_info.message_ids = "MID573D35A4BB4F4, MID573D35A4BB4A2";

    result = delete_messages(&user_info, &delete_messages_info);
    print_result(result);

    return 0;
}
#endif
```

