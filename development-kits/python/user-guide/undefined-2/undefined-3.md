# 이미지 삭제

```python
import sys
from sdk.api.image import Image
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to delete images through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # image_id is must be entered
    image_id = "IMG57A44C8F5DC06"
    cool = Image(api_key, api_secret)

    try:
        response = cool.delete_images(image_id)
        print("Success Count : %s" % response['success_count'])
        print("Error Count : %s" % response['error_count'])
        print("Error List : %s" % response['error_list'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

