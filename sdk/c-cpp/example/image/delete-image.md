{% include "../../../fragments/image/delete-image.md" %}




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
	delete_images_opt delete_images_info = delete_images_opt_init();

	delete_images_info.image_ids = "IMG5730547c64fa8, IMG57305482a2296";

	result = delete_images(&user_info, &delete_images_info);
	print_result(result);

	return 0;
}
#endif
```
