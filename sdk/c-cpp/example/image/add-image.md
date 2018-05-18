{% include "../../../fragments/image/add-image.md" %}




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
	upload_image_opt upload_image_info = upload_image_opt_init();

	upload_image_info.image = "./image.jpg";
	// upload_image_info.encoding = "binary";

	result = upload_image(&user_info, &upload_image_info);
	print_result(result);

	return 0;
}
#endif
```