# 이미지 정보

업로드된 이미지의 정보를 리턴합니다.

## Resource URL

`https://solapi.com/images/3/[imageId]/getImageInfo`

## Request Syntax

```javascript
{
  // 입력 사항이 없습니다.
}
```

### Required Parameters

필수적으로 입력해야 할 사항이 없습니다.

### Optional Parameters

선택 옵션 사항이 없습니다.

### Sample Request

## Response Syntax

```javascript
{
  "imageId": "String",
  "imageType": "String",
  "fileSize": Number,
  "width": Number,
  "height": Number
}
```

* `imageType` - 이미지의 형식, 업로드 할 때 서버에서 자동으로 jpeg 형식으로 변환됩니다.
* `fileSize` - 바이트 단위의 파일 크기
* `width` - 이미지의 픽셀 단위 가로 크기
* `height` - 이미지의 픽셀 단위 세로 크기

### Sample Response

```javascript
{
  "imageId": "IMG587C220F0734A",
  "fileSize": 245000,
  "width": 800,
  "height": 600
}
```

### Errors

아래 오류 중 하나가 발생 할 수도 있습니다.

`ResourceNotFound` - 존재하지 않는 이미지, TTL이 만료되었거나 올바르지 않은 이미지ID 입력. HTTP Status Code: 404

공통적으로 일어날 수 있는 오류 코드를 확인하시려면 오류코드 를 참고하세요.

