# 서버에 이미지 등록

```python
import sys
from sdk.api.image import Image
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to upload image through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # image is must be entered
    image = "test.jpg" # image file
    cool = Image(api_key, api_secret)

    try:
        response = cool.upload_image(image)
        print("Image ID : %s" % response['image_id'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

