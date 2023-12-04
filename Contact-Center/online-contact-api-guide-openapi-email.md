## Contact Center > Online Contact > API 가이드 > 이메일 설정
### 대표계정 생성
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/create.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/create.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|대표계정 생성|HTTPS  |POST    |UTF-8|JSON    |서비스 대표계정 생성. (생성 후 수정 불가) 형식: **@oc.toast.com|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|서비스 ID，URL PATH 내에 설정한{serviceId}|
|이메일 정보	|mail	|String	|O	|이메일 정보(예:mail@oc.toast.com의 mail 부분)|

#### Query String

- mail=mail

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|result.content	|displayMail	|String	|X	  |발신자 주소|
|	              |external	    |String	|X	  |외부계정 목록|
|	              |mail	        |String	|O	|대표계정 주소 : mail@oc.toast.com|
|	              |name	        |String	|X	  |발신자 이름|
|	              |template	    |String	|X	  |이메일 형식|
|	              |updatedDt	  |Long	  |X	  |업데이트 시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "displayMail":"noreply@toast.com",
            "external":{},
            "mail":"mail@oc.toast.com",
            "name":"noreply",
            "template":"<p>#{content}</p>",
            "updatedDt":1597369998000
        }
    }
}
```

### 이메일 정보 조회
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|이메일 정보 조회|HTTPS  |GET    |UTF-8|JSON    |해당 서비스 모든 이메일 정보 조회|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	|serviceId	|String	|O	|서비스 ID，URL PATH 내에 설정한{serviceId}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|----|-----|-----------|-----|----|
|result.content	|displayMail	|String	 |X	|발신자 주소|
|	              |external	    |String	 |X	|외부계정 목록|
|       	      |mail	        |String	 |O	|대표계정 주소 : mail@oc.toast.com|
|	              |name	        |String	 |X	|발신자 이름|
|	              |template	    |String	 |X	|이메일 레이아웃|
|	              |updatedDt	  |Long		 |X  |업데이트 시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "displayMail":"noreply@toast.com",
            "external":{},
            "mail":"mail@oc.toast.com",
            "name":"noreply",
            "template":"<p>#{content}</p>",
            "updatedDt":1597371255000
        }
    }
}
```

### 외부계정 유효성 체크
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external/verify.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external/verify.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 유효성 체크|HTTPS  |POST    |UTF-8|JSON    |외부계정 유효성 체크|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|서비스 ID	     |serviceId	   |String	|O	|서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부 계정 정보	|request body	|String	  |O	|외부계정 정보(JSON)|
|	             |id	         |Integer	 |X   |외부계정 ID (신규 생성시에는 필요 없고 수정 시에만 필요)|
|	             |name	       |String	 |O	 |외부계정 구분 명칭(길이:min=1, max=20)|
|	             |active	     |Boolean	 |O	 |외부계정 상태(true:활성화 ,false:비활성화), 수정 시에만 상태 전달 필요|
|	             |host	       |String	 |O	 |메일 서버|
|	             |port	       |Integer  |O	 |포트(예:993)|
|	             |ssl	         |Boolean	 |O	 |ssl 사용여부(true:사용,false:미사용)|
|	             |mail	       |String	 |O	 |외부계정 주소(정확한 이메일 주소)|
|	             |password	   |String	 |O	 |외부계정 비밀번호(서비스를 이용하는 기간 동안 입력한 이메일 주소와 비밀번호가 보관됩니다.)|
|	             |mailDel   	 |Boolean	 |O	 |원본 남기기 기능 사용 여부(true:삭제(이메일이 티켓으로 전환되면 해당 이메일이 자동으로 삭제 됨）,false:보류)|

#### Request Body
```
{
    "id":21,
    "name":"octest1",
    "active":true
    "host":"imap.163.com",
    "port":993,
    "ssl":true
    "mail":"octest1@163.com",
    "password":"yourpassword",
    "mailDel":false
}
```

#### 결과 데이터
|명칭	   |변수	   |데이터 타입	|필수	|설명|
|-------|--------|-------------|-----|---|
|result	|content	|String    	 |O	   |SUCCESS(성공)|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
         "content":"SUCCESS",
    }
}
```

### 외부계정 등록
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 등록|HTTPS|POST|UTF-8|JSON|외부계정 등록(유효성 체크 후 등록 가능)|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	     |serviceId	    |String	  |O	  |서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부 계정 정보	 |request body	|Stirng 	|O	  |외부계정 정보(JSON)|
|	              |name	         |String	 |O	   |외부계정 구분 명칭(길이:min=1, max=20)|
|	              |host	         |Stirng	 |O	   |메일 서버|
|	              |port 	       |Integer	 |O	   |포트(예:993)|
|	              |ssl	         |Boolean	 |O	   |ssl 사용여부(true:사용,false:미사용)|
|       	      |mail	         |String	 |O	   |외부계정 주소(정확한 이메일 주소)|
|	              |password	     |String	 |O	   |외부계정 비밀번호(서비스를 이용하는 기간 동안 입력한 이메일 주소와 비밀번호가 보관됩니다.)|
|	              |mailDel	     |Boolean	 |O	   |원본 남기기 기능 사용 여부(true:삭제(이메일이 티켓으로 전환되면 해당 이메일이 자동으로 삭제 됨）,false:보류)|

#### Request Body
```
{
    "name":"octest1",
    "host":"imap.163.com",
    "port":993,
    "ssl":true
    "mail":"octest1@163.com",
    "password":"yourpassword",
    "mailDel":false
}
```

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|----|-----------|-----|----|
|result.content	|id	      |Integer	|X	  |외부계정 ID|
|               |name	    |String	  |O	|외부계정 구분 명칭|
|	              |active	  |Boolean	|O	|외부계정 상태(고정 값:true)|
|	              |host	    |String	  |O	|메일 서버|
|	              |port	    |Integer	|O	|포트(예:993)|
|               |ssl	    |Boolean	|O	|ssl 사용여부(true:사용,false:미사용)|
|	              |mail	    |String	  |O	|외부계정 주소|
|	              |password	|String	  |O	|외부계정 비밀번호|
|	              |mailDel	|Boolean	|O	|원본 남기기 기능 사용 여부(true:삭제,false:보류)|
|	              |createdDt	|Long	  |X	  |생성시간|
|	              |updatedDt	|Long   |X		|수정시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "id":16,
            "name":"octest1",
            "active":true
            "host":"imap.163.com",
            "port":993,
            "ssl":true
            "mail":"octest1@163.com",
            "password":"********",
            "mailDel":false,
            "createdDt":1597382469685,
            "updatedDt":1597382469685
        }
    }
}
```

### 외부계정 수정
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 수정|HTTPS|PUT|UTF-8|JSON|외부계정 수정(유효성 체크 후 수정 가능)|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	     |serviceId	    |String	  |O	  |서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부계정 ID	   |id	         |Integer   |O	 |외부계정 ID,URL PATH내에 설정된 {id}|
|외부계정 정보	 |request body	|String	  |O	  |외부계정 정보(JSON)|
|	              |name	         |String	 |O	   |외부계정 구분 명칭(길이:min=1, max=20)|
|	              |active	       |Boolean	 |X	   |외부계정 상태(true:활성화,false:비활성화)|
|	              |host	         |String	 |O	   |메일 서버|
|	              |port	         |Integer	 |O	   |포트(예:993)|
|	              |ssl	         |Boolean	 |O	   |ssl 사용여부(true:사용,false:미사용)|
|	              |mail	         |String	 |O	   |외부계정 주소(정확한 이메일 주소)|
|	              |password	     |String	 |O	   |외부계정 비밀번호(서비스를 이용하는 기간 동안 입력한 이메일 주소와 비밀번호가 보관됩니다.)|
|	              |mailDel	     |Boolean	 |O	   |원본 남기기 기능 사용 여부(true:삭제(이메일이 티켓으로 전환되면 해당 이메일이 자동으로 삭제 됨）,false:보류)|

#### Request Body
```
{
    "name":"octest1",
    "host":"imap.163.com",
    "port":993,
    "ssl":true
    "mail":"octest1@163.com",
    "password":"yourpassword",
    "mailDel":false
}
```

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|----|-----|------------|----|----|
|result.content	|id	    |Integer	|X	  |외부계정 ID|
|               |name	  |String	  |O	|외부계정 구분 명칭|
|	              |active	|Boolean	|O	|외부계정 상태(true:활성화,false:비활성화)|
|	              |host	  |String	  |O	|메일 서버|
|               |port	  |Integer	|O	|포트(예:993)|
|               |ssl	  |Boolean	|O	|ssl 사용여부(true:사용,false:미사용)|
|	              |mail	  |String	  |O	|외부계정 주소|
|	              |password	|String	|O	|외부계정 비밀번호|
|	              |mailDel	|Boolean	|O	|원본 남기기 기능 사용 여부(true:삭제,false:보류)|
|	              |createdDt	|Long		|X   |생성시간|
|               |updatedDt	|Long		|X  |수정시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "id":null,
            "name":"octest1",
            "active":null
            "host":"imap.163.com",
            "port":993,
            "ssl":true
            "mail":"octest1@163.com",
            "password":"********",
            "mailDel":false,
            "createdDt":null,
            "updatedDt":1597382469685
        }
    }
}
```

### 외부계정 활성화
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}/enable.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}/enable.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 활성화|HTTPS|PUT|UTF-8|JSON|비활성화 상태 외부계정을 활성화|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	   |serviceId	|String	 |O	 |서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부계정 ID	|id	       |Integer	|O	|외부계정 ID,URL PATH내에 설정된 {id}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|----|
|result.content	|id	        |Integer  |X		  |외부계정 ID|
|	              |name	      |String	  |O	  |외부계정 구분 명칭|
|	              |active	    |Boolean	|O	  |외부계정 상태(고정 값 : true)|
|               |host	      |String	  |O	  |메일 서버|
|	              |port	      |Integer	|O	  |포트(예:993)|
|	              |ssl	      |Boolean	|O	  |ssl 사용여부(true:사용,false:미사용)|
|	              |mail	      |String	  |O	  |외부계정 주소|
|	              |password	  |String	  |O	  |외부계정 비밀번호|
|	              |mailDel	  |Boolean	|O	  |원본 남기기 기능 사용 여부(true:삭제,false:보류)|
|	              |createdDt	|Long		  |X     |생성시간|
|	              |updatedDt	|Long		  |X     |수정시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "id":21,
            "name":"octest1",
            "active":true
            "host":"imap.163.com",
            "port":993,
            "ssl":true
            "mail":"octest1@163.com",
            "mailDel":false,
            "createdDt":1578376856000,
            "updatedDt":1597384423000
        }
    }
```

### 외부계정 비활성화
#### 인터페이스 설명

- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}/disable.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}/disable.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 비활성화|HTTPS|PUT|UTF-8|JSON|활성화 상태 외부계정을 비활성화|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	   |serviceId	|String	 |O	 |서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부계정 ID	|id	       |Integer	|O	|외부계정 ID,URL PATH내에 설정된 {id}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|----|-----------|-----|----|
|result.content	|id	        |Integer	|X	  |외부계정 ID|
|	              |name	      |String	  |O	|외부계정 구분 명칭|
|	              |active	    |Boolean	|O	|외부계정 상태(고정 값 : false)|
|	              |host	      |String 	|O	|메일 서버|
|	              |port	      |Integer	|O	|포트(예:993)|
|	              |ssl	      |Boolean	|O	|ssl 사용여부(true:사용,false:미사용)|
|	              |mail	      |String	  |O	|외부계정 주소|
|	              |password	  |String	  |O	|외부계정 비밀번호|
|	              |mailDel	  |Boolean	|O	|원본 남기기 기능 사용 여부(true:삭제,false:보류)|
|               |createdDt	|Long		  |X   |생성시간|
|	              |updatedDt	|Long		  |X   |수정시간|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":{
            "id":21,
            "name":"octest1",
            "active":false
            "host":"imap.163.com",
            "port":993,
            "ssl":true
            "mail":"octest1@163.com",
            "mailDel":false,
            "createdDt":1578376856000,
            "updatedDt":1597384423000
        }
    }
```

### 외부계정 삭제
#### 인터페이스 설명
- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail/external/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|외부계정 삭제|HTTPS|DELETE|UTF-8|JSON|비활성화 상태 외부계정 삭제|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	   |serviceId	|String	 |O	 |서비스 ID，URL PATH 내에 설정한{serviceId}|
|외부계정 ID	|id	       |Integer	|O	|외부계정 ID,URL PATH내에 설정된 {id}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|----|------------|-----|---|
|result.content|		|String|X		|"SUCCESS":삭제 성공|

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":{
        "content":"SUCCESS"
    }
}
```

### 이메일 정보 저장
#### 인터페이스 설명
- URL: https://{domain}.oc.toast.com/{serviceId}/openapi/v1/mail.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/openapi/v1/mail.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|이메일 정보 저장|HTTPS|POST|UTF-8|JSON|이메일 정보 저장|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|----------|-----|---|
|서비스 ID	        |serviceId	   |String	|O	|서비스 ID|
|이메일 설정 정보	 |request body	|String	 |O	 |이메일 설정 정보(JSON)|
|	                 |name	        |String	 |X	 |발신자 이름(길이:min = 0, max = 45)|
|	                 |displayMail	  |String	 |X	 |발신자 주소(예：noreply@oc.toast.com)|
|	                 |template	    |String	 |X	 |이메일 레이아웃. 예) \<p\>\#\{content\}\<\/p\> 해당 이메일 레이아웃은 모든 이메일에 적용됩니다. #{content} 태그는 반드시 추가해야 합니다.|

#### Request Body
```
{
    "name":"noreply",
    "displayMail":"noreply@oc.toast.com",
    "template":"<p>#{content}</p>"
}
```

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|----|-----------|-----|----|
|result	|		|	        |      |    |

#### Response Body
```
{
    "header":{
        "resultCode":200,
        "resultMessage":"",
        "isSuccessful":true
    },
    "result":null
}
```
