## Contact Center > Online Contact > API 가이드 > 고객정보 연동

고객정보 연동은 Online Contact이 아닌 자체 사용중인 외부 서비스의 정보를 API 설정을 통해 티켓관리 화면에서 조회할 수 있는 기능입니다. 

### API 인증 방법

#### Security Key
![OpenAPI_SecurityKey](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-openapi-customer-data_img0010.png)

[고객정보관리 → 고객정보연동 → API 설정]에서 **API 암호화 여부**를 '예'로 설정하면, **암호화 키**가 생성됩니다.

생성된 키로 API 인증에 활용할 수 있습니다.

#### Authorization 문자열 생성 방법

HmacSHA256로 암호화하거나, (request URI + 파라미터 값(json) + 현재 UTC시간 값)문자열에 대해 암호화하여 Authorization 문자열을 생성할 수 있습니다.

##### Java 예시

```
String token= request.getHeader("Authorization");
String time = request.getHeader("X-TC-Timestamp");
if (!StringUtils.isNumeric(time)) {
    logger.error("X-TC-Timestamp is not numeric: " + time);
    throw new Exception("error.bad_request");
}
DateTime date = null;
date = new DateTime(Long.parseLong(time));
if (date.minusMinutes(5).isAfterNow() || date.plusMinutes(5).isBeforeNow()) {
    logger.error("X-TC-Timestamp is expired: " + time + ", now timestamp: " + Calendar.getInstance().getTimeInMillis());
    throw new Exception("error.bad_request");
}

String apiKey = "bf7769e5321448de88838cdb";
String content= new String(IOUtils.toByteArray(request.getInputStream()), StandardCharsets.UTF_8) + time;

SecretKeySpec signingKey = new SecretKeySpec(apiKey.getBytes(StandardCharsets.UTF_8), "HmacSHA256");
Mac mac = Mac.getInstance(signingKey.getAlgorithm());
mac.init(signingKey);
byte[] rawHmac = mac.doFinal(content.getBytes(StandardCharsets.UTF_8));
String localAuthorization = new String(Base64.encodeBase64(rawHmac));
logger.debug("Local token: " + localAuthorization);
if (StringUtils.equals(token, localAuthorization)) {
    return true;
}  else {
        logger.info("Local sha2 token: " + localAuthorization);
        return false;
    }
}
```

### 고객정보연동 API

#### 인터페이스 설명

|인터페이스 명|프로토콜|호출방향|인코딩|요청 파라미터 형식|URL|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|---------|
|고객정보연동 API|HTTPS  |POST    |UTF-8|JSON|기본 URL|공통 인증|

#### 요청 파라미터 정의

|명칭|변수|데이터 타입|필수|설명|
|----|----|----|---------|----|
|설정한 조회 항목  |callNum|String  |O ||
|                |nation |String  |  ||

#### Request Body

```
{ 
  "callNum":"1",
  "nation":"korea"
}
```

#### 결과 데이터

|명칭|변수|데이터 타입|필수|설명|
|----|---|-----------|---|----|
|설정한 결과 항목   |userName|String| | |
|                |id |String| | |

#### Response Body

```
{
  "data": {
    "userName": "test",
    "id": "testId"
    }
}
```

### 리턴 결과

#### 파라미터 정의

|명칭|변수|데이터 타입|필수|설명|
|----|----|----------|---|----|
|성공 시 리턴 결과  |data|JSON   |O   | |
|                  |OC에서의 결과 항목 설정값|String |O   | |

|명칭|변수|데이터 타입|필수|설명|
|----|----|----------|---|----|
|실패 시 리턴 결과 | error | JSON | O | |
|              | code | String | O | |
|              | message | String | O | |
|              | detail  | String | O | |

#### HTTP 상태 코드

|리턴 코드 정보 | Online Contact 표시 메시지 |
|--------------|------------|
|200 : SUCCESS | 조회 성공           |
|400 : Bad Request | 조회 결과가 없습니다. |
|403 : Forbidden   | 요청한 서버에 조회 권한이 없습니다. |
|404 : Not Data Found | 요청한 서버에 에러가 있습니다. |
|500 : Server Error   | 오류가 발생하였습니다. |

#### 리턴 결과 예시

```
200 : OK
{
  "data": {
    "userNo": "0",
    "userId": "string",
    "gameCode": "string",
     "cashReal": "0",
     "cashBonus": "0",
     "cashTotal": "0"
    }
}

```
```
Failure case : HTTP Status Code != 200 AND error object
{
  "error": {
    "code": 911,
    "message": "Not existing user.",
    "detail": null
  }
}
```
