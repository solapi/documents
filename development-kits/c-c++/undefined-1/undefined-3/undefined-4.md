# 기본 발신번호 설정

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
    set_default_opt set_default_info = set_default_opt_init();

    set_default_info.handle_key = "SID573D71F010D6B";
    set_default_info.site_user = "__private__";

    result = set_default(&user_info, &set_default_info);
    print_result(result);

    return 0;
}
#endif
```

