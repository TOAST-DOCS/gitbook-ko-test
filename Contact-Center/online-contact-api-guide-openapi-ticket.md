## Contact Center > Online Contact > API 가이드 > 문의 내역

### 고객 티켓 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/list.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/list.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|고객 티켓 리스트 |HTTPS  |POST    |UTF-8|JSON    |검색 조건을 통해 조건에 맞는 고객의 티켓 리스트 노출|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-------|------|---------------|--------|-----|----|
|서비스 ID	       |serviceId	|String	    |path	|O	|서비스 ID，URL PATH 내에 설정한 {serviceId}|
|유저 코드	       |usercode	|String	    |path	|O	|유저 코드(유일한 값)，URL PATH 내에 설정한{usercode}|
|카테고리 ID	   |categoryId	|Integer	|query	|X	|카테고리(접수유형) ID|
|티켓 상태	       |status	    |String  	|query	|X	|티켓 상태. new: 미할당, open: 처리중, reply: 보류, solved: 해결, closed: 완료|
|언어 코드	       |language	|String	    |query	|X	|서비스 헬프센터 기본 언어 코드|
|채널	           |source  	|String 	|query	|X	|문의 채널(web: PC웹, spweb: 모바일 웹, api: API. 복수의 채널 조회 시 콤마로 구분하여 사용(예: web,spweb,api). 기본 값은 web,spweb,api|
|정렬방식	       |sort	     |String	|query	|X	|정렬 순서(기본값: updatedDt:desc; 정렬 형식: 오름차순:asc, 내림차순:desc)|
|페이지	           |page	     |Integer	|query	|X	|기본 값: 1|
|1페이지 노출 건수	|pageSize	  |Integer	 |query	 |X	 |기본 값: 10; max=200|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|-----------|---|
|result.contents	|ticketId	        |String		    |티켓 ID|
|	                |subject	        |String		    |티켓 제목|
|	                |categoryId	        |Integer		|접수유형 ID|
|	                |categoryName	    |String		    |접수유형 명|
|	                |categoryFullName	|String		    |카테고리 전체 경로(>로 각 뎁스 연결)|
|	                |status 	        |String		    |티켓 상태. new: 미할당, open: 처리중, reply: 보류, solved: 해결, closed: 완료|
|	                |statusName	        |String		    |티켓 상태 명|
|	                |createdDt	        |Long		    |티켓 생성시간|
|	                |updatedDt	        |Long		    |티켓 업데이트 시간|
|	                |displayDt	        |String		    |노출 시간(yyyy.MM.dd)|
|result 	        |total	            |Integer		|총 건수|
|	                |pages	            |Integer		|총 페이지 수|
|	                |pageNum	        |Integer		|현재 페이지|
|                   |pageSize	        |Integer		|1페이지 당 노출 건수|

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
        "ticketId": "T1658213182227yb9hI",		
        "subject": "유형11",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "reply",		
        "statusName": "추가 확인",		
        "content": null,		
        "createdDt": 1658213182000,		
        "updatedDt": 1658215682000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T16582131010751o8BM",		
        "subject": "유형10",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "solved",		
        "statusName": "답변 완료",		
        "content": null,		
        "createdDt": 1658213101000,		
        "updatedDt": 1658215702000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658213078429EFmxm",		
        "subject": "유형9",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "closed",		
        "statusName": "최종 완료",		
        "content": null,		
        "createdDt": 1658213078000,		
        "updatedDt": 1658215720000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658213060072Witj6",		
        "subject": "유형8",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "open",		
        "statusName": "문의 확인",		
        "content": null,		
        "createdDt": 1658213060000,		
        "updatedDt": 1658215646000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658212816320fVxqS",		
        "subject": "유형7",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658212816000,		
        "updatedDt": 1658212816000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658211072628h00Qf",		
        "subject": "유형6",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658211073000,		
        "updatedDt": 1658211073000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658211058049HP1U0",		
        "subject": "유형5",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658211058000,		
        "updatedDt": 1658211058000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T165821104308563aoM",		
        "subject": "유형4",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658211043000,		
        "updatedDt": 1658211043000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658211028245FwMKd",		
        "subject": "유형3",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658211028000,		
        "updatedDt": 1658211028000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      },		
      {		
        "ticketId": "T1658211012753VCyy2",		
        "subject": "유형2",		
        "categoryId": 2542,		
        "categoryName": "유형1-1-1-1-1",		
        "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
        "status": "new",		
        "statusName": "접수 완료",		
        "content": null,		
        "createdDt": 1658211013000,		
        "updatedDt": 1658211013000,		
        "contents": null,		
        "attachments": null,		
        "displayDt": "2022.07.19"		
      }		
    ],		
    "total": 12,		
    "pages": 2,		
    "pageNum": 1,		
    "pageSize": 10		
  }		
}		
```

### 티켓 상세
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/detail.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/detail.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|티켓 상세  |HTTPS  |GET    |UTF-8|JSON    |고객이 접수한 티켓 상세 조회|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형 |필수	|설명|
|-----|-----|-----------|-----|---|------|
|서비스 ID	|serviceId	|String	|path	|O	|서비스 ID，URL PATH 내에 설정한 {serviceId}|
|아이디	    |usercode	|String	|path	|O	|아이디(사용자 고유 ID), 문의 접수 시의 usercode|
|티켓 ID	|ticketId	|String	|path	|O	|티켓 ID|
|언어코드	|language	 |String	|query	|X	|서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|-----------|--------|
|result.content	|ticketId	|String		    |티켓 ID|
|	            |subject	|String		    |서비스 ID|
|	            |categoryId	|Integer		|카테고리(접수유형) ID|
|	            |categoryName	|String		|카테고리 명|
|	            |categoryFullName	|String		|카테고리 전체 경로(>로 각 뎁스 연결)|
|	            |status	            |String		|티켓 상태. new: 미할당, open: 처리중, reply: 보류, solved: 해결, closed: 완료|
|	            |statusName	        |String		|티켓 상태 명|
|	            |content	        |String		|문의 내용|
|	            |createdDt	        |Long		|생성 시간|
|	            |updatedDt	        |Long		|수정 시간|
|	            |contents	        |Array		|티켓 상세 내용|
|	            |contents.content	|String		|내용 상세|
|	            |contents.type	    |String		|문의 유형. enduser: 문의(접수 완료), csuser: 답변(접수 완료)|
|	            |contents.typeName	|String		|내용 유형 명|
|	            |contents.createdDt	|Long		|티켓 처리 시간|
|	            |contents.displayDt	|String		|내용 노출 시간(yyyy.MM.dd)|
|	            |contents.attachments	|Array		|티켓 처리 내용 첨부파일|
|	            |contents.attachments.attachmentId	|String		|티켓 처리 내용 첨부파일 ID|
|	            |contents.attachments.fileName	    |String		|티켓 처리 내용 첨부파일 명|
|	            |contents.attachments.contentType	|String		|티켓 처리 내용 첨부파일 유형|
|	            |contents.attachments.disposition	|String		|티켓 처리 내용 첨부파일 처리 방식(attachment: 첨부파일)|
|	            |contents.attachments.size	        |Long		|티켓 처리 내용 첨부파일 사이즈|
|	            |contents.attachments.createdDt	    |Long		|티켓 처리 내용 첨부파일 업로드 시간|
|	            |attachments	                    |Array		|티켓 문의 첨부파일|
|	            |attachments.attachmentId	        |String		|티켓 문의 첨부파일 ID|
|               |attachments.fileName	            |String		|티켓 문의 첨부파일 명|
|	            |attachments.contentType	        |String		|티켓 문의 첨부파일 유형|
|	            |attachments.disposition	        |String		|티켓 문의 첨부파일 처리 방식(attachment: 첨부파일)|
|	            |attachments.size	                |Long		|티켓 문의 첨부파일 사이즈|
|	            |attachments.createdDt	            |Long		|티켓 문의 첨부파일 업로드 시간|
|	            |displayDt	                        |String		|노출 시간(yyyy.MM.dd)|
|result	        |total	                            |Integer	|총 건수|
|	            |pages	                            |Integer	|총 페이지 수|
|	            |pageNum	                        |Integer	|페이지|
|	            |pageSize	                        |Integer	|페이지 당 건수|

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
      "ticketId": "T1658199661153IXTfw",		
      "subject": "유형",		
      "categoryId": 2542,		
      "categoryName": "유형1-1-1-1-1",		
      "categoryFullName": "유형1>유형1-1>유형1-1-1>유형1-1-1-1>유형1-1-1-1-1",		
      "status": "solved",		
      "statusName": "답변 완료",		
      "content": "문의내용",		
      "createdDt": 1658199661000,		
      "updatedDt": 1658279983000,		
      "contents": [		
        {		
          "content": "<p>solved</p>",		
          "type": "reply",		
          "typeName": "답변",		
          "createdDt": 1658279983000,		
          "displayDt": "2022.07.20",		
          "attachments": [		
            {		
              "attachmentId": "a9e126cf01654631acc2d1e56e8c694e",		
              "fileName": "image.png",		
              "contentType": "image/png",		
              "disposition": "attachment",		
              "size": 90576,		
              "createdDt": 1658279969000		
            }		
          ]		
        },		
        {		
          "content": "<p>append commnet</p>",		
          "type": "enduser",		
          "typeName": "질문",		
          "createdDt": 1658279813000,		
          "displayDt": "2022.07.20",		
          "attachments": null		
        },		
        {		
          "content": "<p>append comment</p>",		
          "type": "enduser",		
          "typeName": "질문",		
          "createdDt": 1658216460000,		
          "displayDt": "2022.07.19",		
          "attachments": null		
        },		
        {		
          "content": "<p>solved</p>",		
          "type": "reply",		
          "typeName": "답변",		
          "createdDt": 1658216406000,		
          "displayDt": "2022.07.19",		
          "attachments": null		
        }		
      ],		
      "attachments": null,		
      "displayDt": "2022.07.19"		
    }		
  }		
}		
```

### 티켓 첨부파일 열기 및 다운로드
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/ticket/attachments/{id}
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/ticket/attachments/{id}

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|티켓 첨부파일 열기 및 다운로드  |HTTPS  |GET    |UTF-8|JSON    |티켓 첨부파일 열기/다운로드|필요 없음   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-------|------|---------------|---------|---|----|
|서비스 ID	    |serviceId	|String	|path   |O	|URL PATH 내에 설정한 {serviceId}|
|첨부한 파일 ID	|id	        |String	|path   |O	|첨부파일 ID, URL PATH 내에 설정한 {id}| 
|처리방식	    |type	    |String	|query  |X	|기본 값은 브라우저로 열기(download: 다운로드, open: 브라우저로 열기）|

#### 결과 데이터
File

### 고객 재문의
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/comment.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/comment.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|고객 재문의  |HTTPS  |POST    |UTF-8|JSON    |티켓 ID 기준으로 고객 재문의|공통 인증|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형 |필수	|설명|
|-------|--------|-----------|-----|---|--------------|
|서비스 ID	|serviceId	|String	|path	|O	|서비스 ID，URL PATH 내에 설정한 {serviceId}|
|아이디	    |usercode	|String	|path	|O	|아이디(사용자 고유 ID), 문의 접수 시의 usercode|
|티켓 ID	|ticketId	|String	|path	|O	|티켓 ID|
|내용	    |comment	|String	|body	|O	|재문의 내용|
|첨부파일	|attachments	|String	|query	|X	|첨부파일 ID. 복수의 파일 첨부시 파일 ID를 (,)로 분리, max는 5건(파일ID1,파일ID2,…,파일ID5)|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|-----------|-------|
|result.content	|content	|String		|재문의 내용|
|	            |type	    |String		|타입. 고정값: enduser|
|               |typeName	|String		|타입 명칭|
|	            |createdDt	|Long		|제출 시간|
|	            |displayDt	|String		|노출 시간(yyyy.MM.dd)|
|	            |attachments	|Array		|첨부파일|
|	            |attachments.attachmentId	|String		|첨부파일 ID|
|	            |attachments.fileName	    |String		|첨부파일 명|
|	            |attachments.contentType	|String		|첨부파일 유형|
|	            |attachments.disposition	|String		|파일 처리방식(attachment: 첨부파일)|
|	            |attachments.size	        |Long		|첨부파일 사이즈|
|	            |attachments.createdDt	    |Long		|첨부파일 업로드 시간|

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
      "content": "<p>append comnment</p>",		
      "type": "enduser",		
      "typeName": null,		
      "createdDt": 1658286589999,		
      "displayDt": null,		
      "attachments": [		
        {		
          "attachmentId": "a9e126cf01654631acc2d1e56e8c694e",		
          "fileName": "image.png",		
          "contentType": "image/png",		
          "disposition": "attachment",		
          "size": 90576,		
          "createdDt": 1658279969000		
        }		
      ]		
    }		
  }		
}		
```
