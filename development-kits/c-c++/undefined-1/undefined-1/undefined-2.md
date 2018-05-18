# 그룹 삭제

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
    delete_groups_opt delete_groups_info = delete_groups_opt_init();

    delete_groups_info.group_ids = "GID573D2C9C8A4CE, GID573D2CB85E4F9";

    result = delete_groups(&user_info, &delete_groups_info);
    print_result(result);

    return 0;
}
#endif
```

