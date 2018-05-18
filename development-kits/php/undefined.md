# 시작하기

Coolsms PHP SDK v2.0 PSR-4에 준수하여 코딩 되어있습니다. 이 의미는 namespace 와 autoload를 이용하여 만들어져 있다는 이야기입니다.  
 [namespacing](http://php.net/manual/en/language.namespaces.rationale.php) 과 [autoloading](http://php.net/manual/en/function.spl-autoload-register.php) 의 개념을 이해하시는 것이 개발 하는데에 있어서 더 도움이 될 것 입니다.

## Step 1. Download SDK

아래 방법중 한 가지를 선택해 다운로드 해주세요.

* Composer를 이용해 다운로드 가능 합니다.   


  `composer require coolsms/php-sdk`

* Coolsms 사이트에서도 다운로드 받으실 수 있습니다. 해당 압축파일에는 Coolsms PHP SDK, 코드 샘플이 포함되어 있습니다. -&gt; [바로가기](https://www.coolsms.co.kr/index.php?mid=download&document_srl=3130218)
* Github를 통해 소스를 가져올 수 있습니다. -&gt; [바로가기](https://github.com/coolsms/php-sdk/releases)

## Step 4. 문자보내기

* 이제 PHP SDK를 사용할 준비가 되었습니다! [Example](undefined-1/)을 통해 사용 방법을 알아보세요.

### 참고사항

10월 16일 이후로 발신번호 사전등록제로 인해 등록된 발신번호로만 문자를 보내실 수 있습니다. 아래 관련링크를 참고 해주세요.

* [발신번호 사전등록제 공지사항](https://www.coolsms.co.kr/index.php?mid=notice&document_srl=3070386)
* [PHP SDK 발신번호 등록 방법](undefined-1/undefined-3/)
* [웹 에서 발신번호 등록하기](https://www.coolsms.co.kr/index.php?mid=service_setup&act=dispSmsconfigSenderNumbers)

#### System requirements

* PHP 5.5 or greater
* The curl extension
* Composer \(optional\)

