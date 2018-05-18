# 메시지 전송

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
    send_group_opt send_group_info = send_group_opt_init();

    send_group_info.group_id = "GID573D2CD5BDFED";

    result = send_group(&user_info, &send_group_info);
    print_result(result);

    return 0;
}
#endif
```

