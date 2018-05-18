# 이미지 삭제

업로드된 이미지를 삭제합니다.

## Resource URL

`https://solapi.com/ImageUpload/3/deleteImages`

## Request Syntax

```javascript
{
  "images": [
    {
      "imageId": "String"
    },
    ...
  ]
}
```

### Required Parameters

* `images` - \[Array\] 형식의 이미지ID 목록

### Optional Parameters

선택 옵션이 없습니다.

### Sample Request

## Response Syntax

```javascript
{
  "errorCount": Number,
  "resultList": [
    {
      "imageId": "String",
      "resultCode": "String"
    }
  ]
}
```

* `errorCount` - 오류 카운트
* `resultList` - Array 형식의 삭제 이미지별 결과가 리턴됩니다.
  * `resultCode` - 아래 코드들 중 하나가 리턴됩니다.
    * `Success` - 성공
    * `ResourceNotFound` - 이미지ID에 해당하는 이미지가 존재하지 않습니다.
    * `InternalError` - 내부 서부 오류로 인해 정상처리 되지 않았습니다.

### Sample Response

```javascript
{
  "imageId": "IMG587C220F0734A"
}
```

## Errors

공통적으로 일어날 수 있는 오류 코드를 확인하시려면 오류코드 를 참고하세요.

