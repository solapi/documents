# 이미지 정보 보기

```python
import sys
from sdk.api.image import Image
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to check image list through CoolSMS Rest API 
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # Optional parameters for your own needs
    params = dict()
    # params["offset"] = "0" # default 0
    # params["limit"] = "20" # default 20
    cool = Image(api_key, api_secret)

    try:
        response = cool.get_image_list(params)
        print("Total Count : %s" % response['total_count'])
        print("Limit : %s" % response['limit'])
        print("Offset : %s" % response['offset'])
        print("List : %s" % response['list'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

