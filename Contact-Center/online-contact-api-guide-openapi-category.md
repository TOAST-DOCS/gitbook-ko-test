## Contact Center > Online Contact > API 가이드 > 문의 접수

### 접수유형 리스트

#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/ticket/categories.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/ticket/categories.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|접수유형 리스트 |HTTPS  |GET    |UTF-8|JSON    |서비스 내 접수유형 리스트 조회|필요 없음   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수 |설명|
|-------|-------|--------------|--------|-----|----|
|서비스 ID	       |serviceId	|String	   |path	|O	|서비스 ID，URL PATH 중{serviceId}에 설정|
|상위 카테고리 ID	|parent	     |Integer	|query	 |X	 |상위 카테고리에 소속된 하위 카테고리 리스트|
|하위 카테고리 ID	|child	     |Integer	|query	 |X	 |하위 카테고리에 소속된 상위 카테고리 리스트|
|언어 코드	        |language	 |String	|query	 |X	 |서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.contents	|categoryId	|Integer		|접수유형 ID|
|	                |parent	    |Integer		|상위 접수유형 ID|
|	                |name	    |String		    |접수유형 명|
|	                |level	    |Integer		|접수유형 레벨(1, 2, 3, 4, 5)|
|	                |path	    |String		    |접수유형 경로(\\\\로 각 뎁스 카테고리 ID 연결)|
|	                |orderNo	|Integer		|표시 순서|
|	                |languages	|Object		    |카테고리 다국어 명|

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
                "categoryId": 2536,	
                "parent": 0,	
                "name": "유형1",	
                "level": 1,	
                "path": "\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1",	
                    "th": "พิมพ์1",	
                    "ja": "タイプ1",	
                    "en": "Type1",	
                    "zh": "类型1"	
                }	
            },	
            {	
                "categoryId": 2537,	
                "parent": 0,	
                "name": "유형2",	
                "level": 1,	
                "path": "\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형2",	
                    "th": "พิมพ์2",	
                    "ja": "タイプ2",	
                    "en": "Type2",	
                    "zh": "类型2"	
                }	
            },	
            {	
                "categoryId": 2538,	
                "parent": 2536,	
                "name": "유형1-1",	
                "level": 2,	
                "path": "\\2536\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1-1",	
                    "th": "พิมพ์1-1",	
                    "ja": "タイプ1-1",	
                    "en": "Type1-1",	
                    "zh": "类型1-1"	
                }	
            },	
            {	
                "categoryId": 2539,	
                "parent": 2536,	
                "name": "유형1-2",	
                "level": 2,	
                "path": "\\2536\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1-2",	
                    "th": "พิมพ์1-2",	
                    "ja": "タイプ1-2",	
                    "en": "Type1-2",	
                    "zh": "类型1-2"	
                }	
            },	
            {	
                "categoryId": 2540,	
                "parent": 2538,	
                "name": "유형1-1-1",	
                "level": 3,	
                "path": "\\2536\\2538\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1-1-1",	
                    "th": "พิมพ์1-1-1",	
                    "ja": "タイプ1-1-1",	
                    "en": "Type1-1-1",	
                    "zh": "类型1-1-1"	
                }	
            },	
            {	
                "categoryId": 2541,	
                "parent": 2540,	
                "name": "유형1-1-1-1",	
                "level": 4,	
                "path": "\\2536\\2538\\2540\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1-1-1-1",	
                    "th": "พิมพ์1-1-1-1",	
                    "ja": "タイプ1-1-1-1",	
                    "en": "Type1-1-1-1",	
                    "zh": "类型1-1-1-1"	
                }	
            },	
            {	
                "categoryId": 2542,	
                "parent": 2541,	
                "name": "유형1-1-1-1-1",	
                "level": 5,	
                "path": "\\2536\\2538\\2540\\2541\\",	
                "orderNo": 0,	
                "languages": {	
                    "ko": "유형1-1-1-1-1",	
                    "th": "พิมพ์1-1-1-1-1",	
                    "ja": "タイプ1-1-1-1-1",	
                    "en": "Type1-1-1-1-1",	
                    "zh": "类型1-1-1-1-1"	
                }	
            }	
        ]	
    }	
}	
```

### 접수유형 필드 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/ticket/field/user/{categoryId}.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/ticket/field/user/{categoryId}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|접수유형 필드 리스트 |HTTPS  |GET    |UTF-8|JSON    |접수유형을 통하여 대응되는 필드 리스트 확인|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수 |설명|
|-------|-------|--------------|-----|-------|----|
|서비스 ID	    |serviceId	|String	   |path	 |O	|서비스 ID, URL PATH 내에 설정한 {serviceId}|
|접수유형 ID	|categoryId	|Integer   |path 	 |O	|접수유형 ID, URL PATH 내에 설정한 {categoryId}|
|언어 코드	    |language	|String	   |query	 |X	|서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.contents	|fieldId	    |Integer		|고객 필드 ID|	
|                   |code	        |String  		|항목 코드|
|	                |type	        |String		    |항목 유형|
|	                |title	        |String		    |항목 명|
|	                |description	|String		    |안내 문구|
|	                |placeholder	|String		    |제시어|
|	                |length	        |Integer		|최대 길이(0: 길이 제한 없음)|
|	                |required	    |Boolean		|필수 항목 여부(true: yes, false: no)|
|	                |encrypt	    |Boolean	 	|저장 시 암호화 여부(true: yes, false: no)|
|	                |holdingText	|Boolean		|클릭 시 삭제 여부(true: yes, false: no)|
|	                |options	    |Array   		|텍스트 박스, 체크박스, 드롭박스, 예:[구분1,구분2,...]|
|	                |value	        |String		    |사용자 입력 값|

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
                "fieldId": 1,		
                "code": "category",		
                "type": "dropdown",		
                "title": "유형",		
                "description": "",		
                "placeholder": "",		
                "length": 0,		
                "required": true,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 3,		
                "code": "mail",		
                "type": "text",		
                "title": "이메일",		
                "description": "",		
                "placeholder": "",		
                "length": 100,		
                "required": true,		
                "encrypt": true,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 5,		
                "code": "subject",		
                "type": "text",		
                "title": "제목",		
                "description": "",		
                "placeholder": "",		
                "length": 200,		
                "required": true,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 6,		
                "code": "content",		
                "type": "textarea",		
                "title": "문의내용",		
                "description": "",		
                "placeholder": "",		
                "length": 5000,		
                "required": true,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 2,		
                "code": "name",		
                "type": "text",		
                "title": "이름",		
                "description": "",		
                "placeholder": "",		
                "length": 100,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 4,		
                "code": "phone",		
                "type": "text",		
                "title": "전화번호",		
                "description": "",		
                "placeholder": "",		
                "length": 30,		
                "required": false,		
                "encrypt": true,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 9,		
                "code": "attachment",		
                "type": "file",		
                "title": "첨부파일",		
                "description": "10MB 이내 모든 이미지 및 허용된 문서 (MS office, hwp, pdf, txt)와 zip 파일을 5개까지 첨부가능합니다.",		
                "placeholder": "",		
                "length": 0,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 18,		
                "code": "typeOne",		
                "type": "text",		
                "title": "구분1",		
                "description": "",		
                "placeholder": "",		
                "length": 200,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 19,		
                "code": "typeTwo",		
                "type": "text",		
                "title": "구분2",		
                "description": "",		
                "placeholder": "",		
                "length": 200,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 720,		
                "code": "caption",		
                "type": "caption",		
                "title": "단순 텍스트 이름",		
                "description": "<div style=\"color:red\">단순 텍스트 설명</div>",		
                "placeholder": "<div style=\"font-size:20px;color:red\">단순 텍스트 내용</div>",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 721,		
                "code": "textbox",		
                "type": "text",		
                "title": "텍스트 박스 이름",		
                "description": "<div style=\"color:red\">텍스트 박스 설명</div>",		
                "placeholder": "텍스트 박스 자리 표시자",		
                "length": 50,		
                "required": true,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 722,		
                "code": "checkbox",		
                "type": "checkbox",		
                "title": "체크박스 이름",		
                "description": "체크박스 설명",		
                "placeholder": "",		
                "length": 50,		
                "required": false,		
                "encrypt": true,		
                "holdingText": true,		
                "options": [		
                    "옵션1",		
                    "옵션2",		
                    "옵션3"		
                ],		
                "value": null		
            },		
            {		
                "fieldId": 723,		
                "code": "dropdown",		
                "type": "dropdown",		
                "title": "드롭박스 이름",		
                "description": "드롭박스 설명",		
                "placeholder": "",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": [		
                    "옵션1",		
                    "옵션2",		
                    "옵션3"		
                ],		
                "value": null		
            },		
            {		
                "fieldId": 724,		
                "code": "radiobutton",		
                "type": "radio",		
                "title": "라디오 버튼 이름",		
                "description": "라디오 버튼 설명",		
                "placeholder": "",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": [		
                    "옵션1",		
                    "옵션2",		
                    "옵션3"		
                ],		
                "value": null		
            },		
            {		
                "fieldId": 725,		
                "code": "date",		
                "type": "date",		
                "title": "일자 이름",		
                "description": "일자 설명",		
                "placeholder": "2022-07-11",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 726,		
                "code": "datetime",		
                "type": "datetime",		
                "title": "일시",		
                "description": "일시",		
                "placeholder": "2022-07-11 00:00",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 727,		
                "code": "dateperiod",		
                "type": "date_period",		
                "title": "기간 일자 이름",		
                "description": "기간 일자 설명",		
                "placeholder": "2022-07-01 ~ 2022-07-31",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 728,		
                "code": "datetimeperiod",		
                "type": "datetime_period",		
                "title": "기간 일시 이름",		
                "description": "기간 일시 설명",		
                "placeholder": "2022-07-01 00:00 ~ 2022-07-31 23:59",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 729,		
                "code": "agreetotheterms",		
                "type": "agree",		
                "title": "동의하기 이름",		
                "description": "안내 문구",		
                "placeholder": "동의 문구",		
                "length": 50,		
                "required": false,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            },		
            {		
                "fieldId": 11,		
                "code": "personalAgree",		
                "type": "agree",		
                "title": "개인정보수집",		
                "description": "수집하는 개인 정보[(필수) 이메일, 휴대폰 번호, 문의내용, (선택) 첨부 파일]는 문의 내용 처리 및 고객 불만을 해결하기 위해 사용되며, <b><span style=\"font-size: 11pt;\">관련 법령에 따라 3년간 보관 후 삭제</span></b>됩니다. 문의 접수, 처리 및 회신을 위해 꼭 필요한 정보이므로 동의해 주셔야 서비스를 이용하실 수 있습니다.",		
                "placeholder": "위, 개인정보 수집 및 활용에 동의합니다.",		
                "length": 0,		
                "required": true,		
                "encrypt": false,		
                "holdingText": true,		
                "options": null,		
                "value": null		
            }		
        ]		
    }		
}		
```

### 티켓 첨부파일 업로드
#### 인터페이스 설명
- URL: https://{domain}.oc.nhncloud.com/{serviceId}/openapi/v1/ticket/attachments/upload.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/openapi/v1/ticket/attachments/upload.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|티켓 첨부파일 업로드 |HTTPS  |POST    |UTF-8|JSON    |서버에 파일 업로드|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수 |설명|
|-------|-------|--------------|-----|-------|----|
|서비스 ID	    |serviceId	|String	|path	    |O	|URL PATH 내에 설정한 {serviceId}|
|업로드 파일	|file	    |File	|formData	|O	|파일을 form로 제출. 파일 지원 형식: jpg, png, gif, bmp, jpeg, tif, tiff, pdf, txt, hwp, xls, xlsx, doc, docx, ppt, pptx, mp3, wav, zip. 파일 사이즈<10M, 파일명 길이<100|

#### 결과 데이터(성공)
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.content	|attachmentId	|String		|첨부파일 ID|
|	            |fileName	    |String		|첨부파일 명|
|	            |contentType	|String		|첨부파일 유형|
|	            |disposition	|String		|파일 처리 방식(attachment: 첨부파일)|
|	            |size	        |Long		|첨부파일 사이즈(byte)|
|               |createdDt	    |Long		|파일 첨부 시간|

#### Response Body(성공)
```
  "header": {	
    "resultCode": 200,	
    "resultMessage": "",	
    "isSuccessful": true	
  },	
  "result": {	
    "content": {	
      "attachmentId": "8f0dc5854d2446b6aa2e6e41a0a2f55c",	
      "fileName": "image.png",	
      "contentType": "image/png",	
      "disposition": "attachment",	
      "size": 90576,	
      "createdDt": null	
    }	
  }	
}	
```

#### 결과 데이터(실패)
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.content	|exception	|String		|고정 값：OcException|
|	            |message	|String		|오류 메시지 (10MB 이하의 파일만 첨부할수 있습니다. / 파일명 최대 길이 초과.(100) / 해당 파일 격식은 첨부할수 없습니다.|

#### Response Body(실패)
```
{
  "header": {
    "resultCode": 400,
    "resultMessage": "해당 파일 격식은 첨부할 수 없습니다.",
    "isSuccessful": false
  },
  "result": {
    "content": {
      "exception": "OcException",
      "message": "해당 파일 격식은 첨부할 수 없습니다."
    }
  }
}
```

### 티켓 생성
#### 인터페이스 설명
- URL: https://{domain}.oc.nhncloud.com/{serviceId}/openapi/v1/ticket.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/openapi/v1/ticket.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|티켓 생성 |HTTPS  |POST    |UTF-8|JSON    |신규 티켓 생성|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수 |설명|
|-------|-------|--------------|-----|-------|----|
|서비스 ID	|serviceId	        |String	 |path	|O	|서비스 ID，URL PATH 내에 설정한 {serviceId}|
|티켓 정보	|request body	    |Object	 |body	|O	|티켓 정보(JSON)|
|카테고리	|categoryId	        |Integer |		|O	|카테고리(접수유형) ID|
|제목	    |subject	        |String	 |	    |O	|제목(max=255)|
|설명	    |content	        |String	 |	    |O	|원칙 상 단순 텍스트만 허용. Base64 내용으로 제출할 경우 티켓 확인시 내용이 많아 문제될 수 있음. 이미지는 첨부파일 형식으로 업로드하거나, 파일 업로드 후 html의 img src=""/{serviceId}/api/v2/ticket/attachments/{attachmentId}""/ 로 불러와서 사용|
|고객 정보	|endUser	        |Object	  |	     |O	 |고객 정보|
|아이디	    |endUser.usercode	|String	  |	     |X	 |ID(회원 고유 ID). 회원 연동 기능을 사용할 경우, 플랫폼 측의 사용자 고유 ID를 usercode로 사용할 수 있으며, 해당 usercode를 통해 회원의 문의 내역을 조회할수 있음. 비회원 문의일 경우 값을 전송할 필요 없음|
|메일	    |endUser.email	    |String	  |	     |O	 |메일(서비스 관리 → 티켓 → 이메일 설정 메뉴에서 메일 정보를 설정하였을 경우, 티켓 처리 시 해당 메일 주소로 고객에게 메일 발송)|
|이름	    |endUser.username	        |String	  |	     |O	 |이름(메일 파라미터 입력 시, 필수 입력 필요. 입력하지 않을 경우 메일 발송 불가)|
|전화  	    |endUser.phone	            |String	  |	     |X  |전화|
|첨부파일	|attachments	            |Array	  |      |X	 |첨부파일(max 5건)|
|첨부파일 ID|attachments.attachmentId	|String   |	 	 |O	 |첨부파일 ID|
|구분1	    |typeOne	                |String	  |	     |X	 |구분1(확장 시스템 필드1)|
|구분2	    |typeTwo	                |String   |		 |X	 |구분2(확장 시스템 필드2)|
|언어	    |language	                |String	  |	     |X	 |언어|
|채널	    |source	                    |String   |		 |X	 |티켓 채널(web: 웹, spweb: 모바일 웹, api: API, 기본 값: web)|
|사용자 필드	|userFields	            |Array	   |	  |X  |사용자 필드|
|항목 코드	    |userFields.code	    |String	   |	  |O  |사용자 필드, 항목 코드|
|사용자 입력 값	|userFields.value	    |String	   |      |O  |사용자 필드의 사용자 입력 값|

userFields.value 파라미터의 필드 유형별 형식은 하기와 같습니다.

- text(단순 텍스트): "사용자 입력 내용"
- checkbox(체크박스): ["구분1"，"구분2"]
- dropdown(드롭박스): "구분1"
- radio(라디오 버튼): "구분1"
- date(날짜): YYYY-MM-DD("2022-07-11")
- datetime(날짜 시간): YYYY-MM-DD HH:mm("2022-07-11 00:00")
- date_period(날짜 범위): YYYY-MM-DD ~ YYYY-MM-DD("2022-07-01 ~ 2022-07-31")
- datetime_period(날짜 시간 범위): YYYY-MM-DD HH:mm ~ YYYY-MM-DD HH:mm("2022-07-01 00:00 ~ 2022-07-31 23:59")
- agree(동의하기): true, false

#### Request Body
```
{	
    "categoryId": "2542", 	
    "subject": "유형", 	
    "content": "문의내용", 	
    "endUser": {	
        "usercode": "st18888", 	
        "email": "enduser_simple@nhn-st.com", 	
        "username": "이름", 	
        "phone": "13333333333"	
    }, 	
    "attachments": [	
        {	
            "attachmentId": "8f0dc5854d2446b6aa2e6e41a0a2f55c"	
        }	
    ], 	
    "typeOne": "구분1", 	
    "typeTwo": "구분2", 	
    "language": "ko", 	
    "source": "web", 	
    "userFields": [	
        {	
            "code": "textbox", 	
            "value": "텍스트 박스 이름"	
        }, 	
        {	
            "code": "checkbox", 	
            "value": [	
                "옵션1", 	
                "옵션2"	
            ]	
        }, 	
        {	
            "code": "dropdown", 	
            "value": "옵션1"	
        }, 	
        {	
            "code": "radiobutton", 	
            "value": "옵션1"	
        }, 	
        {	
            "code": "date", 	
            "value": "2022-07-11"	
        }, 	
        {	
            "code": "datetime", 	
            "value": "2022-07-11 00:00"	
        }, 	
        {	
            "code": "dateperiod", 	
            "value": "2022-07-01 ~ 2022-07-31"	
        }, 	
        {	
            "code": "datetimeperiod", 	
            "value": "2022-07-01 00:00 ~ 2022-07-31 23:59"	
        }, 	
        {	
            "code": "agreetotheterms", 	
            "value": "true"	
        }	
    ]	
}	
```

#### 결과 데이터(성공)
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.content	|ticketId	    |String		|티켓 ID|
|	            |categoryId	    |int		|접수유형 ID|
|	            |subject	    |String		|티켓 제목|
|	            |content	    |String		|티켓 내용|
|	            |status	        |String		|티켓 상태(고정값: new(미힐당); open(처리중); closed(처리 완료)|
|	            |createdDt	    |Long		|티켓 생성 시간|
|	            |updatedDt	    |Long		|티켓 업데이트 시간|
|	            |attachments	|Array		|첨부파일|
|	            |attachments.attachmentId	|String		|첨부파일 ID|
|	            |attachments.fileName	    |String		|첨부파일 명|
|	            |attachments.contentType	|String		|첨부파일 유형|
|               |attachments.disposition	|String		|파일 처리방식(attachment: 첨부파일)|
|	            |attachments.size	        |String		|첨부파일 사이즈(byt)|
|	            |attachments.createdDt	    |String		|티켓 업데이트 시간|

#### Response Body(성공)
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
      "categoryName": null,	
      "categoryFullName": null,	
      "status": "new",	
      "statusName": null,	
      "content": "문의내용",	
      "createdDt": 1658199661151,	
      "updatedDt": 1658199661151,	
      "contents": null,	
      "attachments": [	
        {	
          "attachmentId": "8f0dc5854d2446b6aa2e6e41a0a2f55c",	
          "fileName": "image.png",	
          "contentType": "image/png",	
          "disposition": "attachment",	
          "size": 90576,	
          "createdDt": 1658192910000	
        }	
      ],	
      "displayDt": null	
    }	
  }	
}	
```

#### 결과 데이터(실패)
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|---------|
|result.contents	|objectName	|String		|사용자 필드: 항목 코드|
|	                |field	    |String		|사용자 필드: 항목 ID|
|	                |validate	|String		|invalid: 무효한 값, length: 최대 길이 초과, required: 항목을 입력하세요|
|	                |key	    |String		|"validate.ticket." + objectName + "." + validate|
|	                |message	|String		|"validate.ticket." + objectName + "." + validate|

#### Response Body(실패)
```
{		
  "header": {		
    "resultCode": 400,		
    "resultMessage": null,		
    "isSuccessful": false		
  },		
  "result": {		
    "contents": [		
      {		
        "objectName": "mail",		
        "field": "3",		
        "validate": "invalid",		
        "key": "validate.ticket.mail.invalid",		
        "message": "validate.ticket.mail.invalid",		
        "rejectValue": ""		
      },		
      {		
        "objectName": "phone",		
        "field": "4",		
        "validate": "length",		
        "key": "validate.ticket.phone.length",		
        "message": "validate.ticket.phone.length",		
        "rejectValue": ""		
      },		
      {		
        "objectName": "textbox",		
        "field": "721",		
        "validate": "length",		
        "key": "validate.ticket.textbox.length",		
        "message": "validate.ticket.textbox.length",		
        "rejectValue": ""		
      },		
      {		
        "objectName": "checkbox",		
        "field": "722",		
        "validate": "invalid",		
        "key": "validate.ticket.checkbox.invalid",		
        "message": "validate.ticket.checkbox.invalid",		
        "rejectValue": ""		
      },		
      {		
        "objectName": "dropdown",		
        "field": "723",		
        "validate": "invalid",		
        "key": "validate.ticket.dropdown.invalid",		
        "message": "validate.ticket.dropdown.invalid",		
        "rejectValue": ""		
      }		
    ]		
  }		
}		
```