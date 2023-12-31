## Security > CAPTCHA > API 가이드
Console에서 CAPTCHA 서비스를 활성화 한 후 다음과 같은 API 호출을 통해 CAPTCHA 서비스를 이용할 수 있습니다.

[표 1] CAPTCHA API 목록

|API|	설명|
|---|---|
|captcha/v1.0/appkeys/{appkey}/keys|	CAPTCHA 인증 키 발급|
|captcha/v1.0/keys/{key}/img|	이미지 CAPTCHA를 출력|
|captcha/v1.0/keys/{key}/sound|	음성 CAPTCHA를 출력|
|captcha/v1.0/appkeys/{appkey}/keys/{key}/verification?answer={answer}|	CAPTCHA 인증 키와 CAPTCHA에 표시된 단어를 검증함|
|captcha/v1.0/appkeys/{appkey}?key={key}|	CAPTCHA 인증 키 expire|

## CAPTCHA 인증 키 발급

[URL]

```
POST   https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/{appKey}/keys
Content-Type  application/json
```

[표 1-1]  CAPTCHA 인증키 발급 Path Parameter

|이름|	자료형|	설명|
|---|---|---|
|appkey|	String|	CAPTCHA appkey|

[표 1-2] CAPTCHA 인증키 발급 response

|이름|	자료형|	설명|
|---|---|---|
|key|	String|	발급 받은 CAPTCHA 인증 키|

[Example Request]

```
URL    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/2b847e2a0afd82e8ff45434f32e8e6e62bf56bcf83ca1befb3739ed9460eb685/keys
```

[Example Response]

```
{
  "header": {
    "resultCode": 0,
    "resultMessage": "SUCCESS"
    "successful": true
  },
  "Key": "a9859757-5b5a-42d1-bc85-c560b0141ec1"
}
```

## 사용자에게 CAPTCHA 출력

[URL]

###Image

```
GET    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/{key}/img
```

###Sound

```
GET    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/{key}/sound
```

[표 2-1] 이미지 CAPTCHA Path Parameter

|이름|	자료형|	설명|
|---|---|---|
|appkey|	String|	CAPTCHA appkey|
|key|	String|	API를 통해 발급 받은 CAPTCHA 인증 키|


###Image CAPTCHA example
[Example Request]

```
URL    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/{key}/img
Html에서 image 태그 사용 예 : <img src="https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/a9859757-5b5a-42d1-bc85-c560b0141ec1/img">
```

[Example Response]

![](http://static.toastoven.net/prod_captcha/img_01.gif)

###Sound CAPTCHA example
```
URL    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/{key}/img
javascript에서 사용 예
    var audio = new Audio("http://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/keys/2155776a-54df-4bc9-a27e-01b84d93a368/sound?timestamp=1513324704457");
    audio.play();
```

## CAPTCHA 확인

[URL]

```
GET    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/{appKey}/keys/{key}/verification?answer={answer}
```

[표 3-1] CAPTCHA 확인 Path Parameter

|이름|	자료형|	설명|
|---|---|---|
|appkey|	String|	CAPTCHA appkey|
|key|	String|	API를 통해 발급 받은 CAPTCHA 인증 키|

[표 3-2]

CAPTCHA 확인 Query Parameter

|이름|	자료형|	설명|
|---|---|---|
|answer|	String|	이미지/음성 CAPTCHA에 표시된 문자|

[Example Request]

```
URL    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/2b847e2a0afd82e8ff45434f32e8e6e62bf56bcf83ca1befb3739ed9460eb685/keys/a9859757-5b5a-42d1-bc85-c560b0141ec1/verification?answer=EAKJH
```

[Example Response]

```
{
  "header": {
    "resultCode": 0,
    "resultMessage": "SUCCESS"
    "successful": true
  }
}
```

## CAPTCHA 인증 키 expire

[URL]

```
DELETE   https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/{appKey}?key={key}
```

[표 4-1] CAPTCHA 인증키 expire Path Parameter

|이름|	자료형|	설명|
|---|---|---|
|appkey|	String|	CAPTCHA appkey|

[표 4-2] CAPTCHA 인증키 expire Query Parameter

|이름|	자료형|	설명|
|---|---|---|
|key|	String|	API를 통해 발급 받은 CAPTCHA 인증 키|

[Example Request]

```
URL    https://kr1-captcha.api.nhncloudservice.com/captcha/v1.0/appkeys/2b847e2a0afd82e8ff45434f32e8e6e62bf56bcf83ca1befb3739ed9460eb685?keys=a9859757-5b5a-42d1-bc85-c560b0141ec1
```

[Example Response]

```
{
  "header": {
    "resultCode": 0,
    "resultMessage": "SUCCESS"
    "successful": true
  }
}
```

