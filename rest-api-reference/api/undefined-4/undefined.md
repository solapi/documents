# 이미지 업로드

## 이미지 업로드

MMS 발송에 필요한 이미지 파일을 업로드 합니다. MMS 발송 때 미리 업로드 된 이미지 파일을 사용하므로 발송과정에서 발생하는 오류률 현저히 줄어듭니다. 이미지 보관 기간은 7일입니다.

## Resource URL

`https://solapi.com/images/3/uploadImage`

## Request Syntax

```javascript
{
  "imageType": "String",
  "base64EncodedImage": "String"
}
```

### Required Parameters

### Optional Parameters

선택 옵션이 없습니다.

### Sample Request

## Response Syntax

```javascript
{
  "imageId": "String"
}
```

### Sample Response

```javascript
{
  "imageId": "IMG587C220F0734A",
}
```

## Errors

공통적으로 일어날 수 있는 오류 코드를 확인하시려면 오류코드 를 참고하세요.

* `ImageTypeNotSupported` - 지원하지 않는 이미지형식 입니다. HTTP Status Code: 403
* `ImageResolutionSizeTooBig` - 이미지 해상도가 허용 가능한 범위를 넘어섭니다. HTTP Status Code: 413
* `FileSizeTooBig` - 이미지파일 300KB 초과. HTTP Status Code: 413

