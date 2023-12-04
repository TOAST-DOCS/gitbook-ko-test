## Contact Center > Online Contact > API 가이드 > 상담원 관리
### 상담원 목록 조회
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/users.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/users.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|상담원 목록 조회|HTTPS  |GET    |UTF-8|JSON    |상담원 목록 조회|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|URL PATH 내에  설정한 {serviceId}|
|사용자 권한	|role	|String	|X	|ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT : 일반 상담원|
|사용자 명	|name	|String	|X	|사용자 명칭|
|페이지 수	|page	|Int	|X	|디폴트 값 = 1|
|페이지 노출 건수	|pageSize	|Int	|X	|디폴트 값 = 10|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|-----------|----|----|
|result.contents	|userId	|I	|O	|사용자 ID|
|	                |usercode	|String	|O	|사용자 Code|
|	                |uuid	|String	|O	|IAM |사용자 ID|
|	                |username	|String	|O	|사용자 명|
|	                |role	|String	|O	|사용자 권한. ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT : 일반 상담원|

#### Response Body
```
{
  "header": {
    "resultCode": 200,
    "resultMessage": "",
    "isSuccessful": true
  },
  "result": {
    "contents": [
      {
        "userId": 10058,
        "usercode": "honggildong",
        "username": "홍길동",
        "uuid": "ef1bd956-6c13-4391-8256-1eb0d840355a",

        "role": "ROLE_FRONT_ADMIN",
      }
    ]
  }
}
```

### 상담원 정보 취득
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/users/{id}.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/users/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|상담원 상세 조회|HTTPS  |GET    |UTF-8|JSON    |상담원 ID를 통해 상담원 상세 정보 조회|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|URL PATH 내에 설정한 {serviceId}|
|사용자 ID	|id	        |Int	|O	|URL PATH 내에 설정한 {id}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|result.contents	|userId	|Int	|O	|사용자ID|
|	                |usercode	|String	|O	|사용자 Code|
|	                |uuid	|String	|O	|IAM 사용자 ID|
|	                |username	|String	|O	|사용자 명|
|	                |role	|String	|O	|사용자 권한. ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT : 일반 상담원|

#### Response Body
```
{
  "header": {
    "resultCode": 200,
    "resultMessage": "",
    "isSuccessful": true
  },
  "result": {
    "content": {
        "userId": 10058,
        "usercode": "honggildong",
        "username": "홍길동",
        ""uuid"": ""ef1bd956-6c13-4391-8256-1eb0d840355a"",
        "role": "ROLE_FRONT_ADMIN",
      }
    }
  }
}
```

### 상담원 추가
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/adduser.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/adduser.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|상담원 추가|HTTPS  |POST    |UTF-8|JSON    |지정한 서비스에 상담원 추가 및 권한 부여|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|URL PATH 내에 설정한 {serviceId}|
|	         |id	       |String	|O	|IAM 사용자 UUID|
|	         |role	     |String	|O	|사용자 권한. ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT：일반 상담원|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|-----------|------|---|
|result.contents	|userId	|Int	|O	|사용자 ID|
|	                |usercode	|String	|O	|사용자 Code|
|	                |uuid	|String	|O	|IAM 사용자 ID|
|	                |username	|String	|O	|사용자 명|
|	                |role	|String |O	|사용자 권한. ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT：일반 상담원|

#### Response Body
```
{
  "header": {
    "resultCode": 200,
    "resultMessage": "",
    "isSuccessful": true
  },
  "result": {
    "content": {
        "userId": 10058,
        "usercode": "honggildong",
        "username": "홍길동",
        "uuid": "ef1bd956-6c13-4391-8256-1eb0d840355a",
        "role": "ROLE_FRONT_ADMIN",
    }
  }
}
```

### 상담원 권한 변경
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/users/{id}.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/users/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|상담원 권한 변경|HTTPS  |PUT    |UTF-8|JSON    |서비스 내 상담원 권한 변경|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|URL PATH 내에 설정한 {serviceId}|
|사용자ID	|id	|String	|O	|URL PATH 내에 설정한 {id}|
|사용자 권한	|role	|String	|O	|ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT：일반 상담원|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|-----------|-----|----|
|result.content	|userId	|Int	|O	|사용자 ID|
|	              |usercode	|String	|O	|사용자 Code|
|	              |uuid	|String |O	|IAM |사용자 ID|
|	              |username	|String	|O	|사용자 명|
|	              |role	|String	|O	|사용자 권한. ROLE_FRONT_ADMIN : 관리자, ROLE_FRONT_AGENT：일반 상담원|

#### Response Body
```
{
  "header": {
    "resultCode": 200,
    "resultMessage": "",
    "isSuccessful": true
  },
  "result": {
    "content": {
        "userId": 10058,
        "usercode": "honggildong",
        "username": "홍길동",
        "uuid": "ef1bd956-6c13-4391-8256-1eb0d840355a",
        "role": "ROLE_FRONT_ADMIN",
    }
  }
}
```

### 상담원 삭제
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/users/{id}.json
- URL(개발): https://{domain}.alpha-oc.toast.com /{serviceId}/openapi/v1/users/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|상담원 삭제|HTTPS/80  |IN(DELETE)    |UTF-8|JSON    |지정한 서비스에서 상담원 삭제|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|URL PATH 내에 설정한 {serviceId}|
|사용자 ID	|id	|Int	|O	|URL PATH 내에 설정한 {id}|

#### 결과 데이터

- 없음
