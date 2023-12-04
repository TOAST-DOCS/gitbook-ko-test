## Contact Center > Online Contact > API 가이드 > FAQ

### 카테고리 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/helpdoc/categories.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/helpdoc/categories.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|카테고리 리스트|HTTPS  |GET    |UTF-8|JSON    |FAQ 카테고리 리스트 취득|필요 없음 |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|----|------|-----------|--------|-----|----|
|서비스 ID	|serviceId	|String	|path	|O	|URL PATH 내에 설정한{serviceId}|
|언어 코드	|language	  |String	|query |X	|서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|-----------|----|
|result.contents	|categoryId	|Integer		|카테고리 ID|
|	                |parent	    |Integer		|상위 카테고리 ID|
|	                |name	      |String		  |카테고리 명|
|	                |level	    |Integer		|뎁스(1, 2, 3)|
|	                |path	      |String		  |뎁스 경로(\level1\level2\)|
|	                |orderNo	  |Integer		|정렬 순서(기본 값: 0)|
|	                |languages	|Object		  |다국어|

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
                "categoryId": 2546,	
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
                "categoryId": 2548,	
                "parent": 2546,	
                "name": "유형1-1",	
                "level": 2,	
                "path": "\\2546\\",	
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
                "categoryId": 2550,	
                "parent": 2548,	
                "name": "유형1-1-1",	
                "level": 3,	
                "path": "\\2546\\2548\\",	
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
                "categoryId": 2547,	
                "parent": 0,	
                "name": "유형2",	
                "level": 1,	
                "path": "\\",	
                "orderNo": 1,	
                "languages": {	
                    "ko": "유형2",	
                    "th": "พิมพ์2",	
                    "ja": "タイプ2",	
                    "en": "Type2",	
                    "zh": "类型2"	
                }	
            },	
            {	
                "categoryId": 2549,	
                "parent": 2546,	
                "name": "유형1-2",	
                "level": 2,	
                "path": "\\2546\\",	
                "orderNo": 1,	
                "languages": {	
                    "ko": "유형1-2",	
                    "th": "พิมพ์1-2",	
                    "ja": "タイプ1-2",	
                    "en": "Type1-2",	
                    "zh": "类型1-2"	
                }	
            },	
            {	
                "categoryId": 2551,	
                "parent": 2548,	
                "name": "유형1-1-2",	
                "level": 3,	
                "path": "\\2546\\2548\\",	
                "orderNo": 1,	
                "languages": {	
                    "ko": "유형1-1-2",	
                    "th": "พิมพ์1-1-2",	
                    "ja": "タイプ1-1-2",	
                    "en": "Type1-1-2",	
                    "zh": "类型1-1-2"	
                }	
            }	
        ]	
    }	
}	
```

### FAQ 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/helpdoc/list.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/helpdoc/list.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|FAQ 리스트|HTTPS  |GET    |UTF-8|JSON    |헬프센터 FAQ 리스트|필요 없음   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-----|----|-----------|-----|----|----|
|서비스 ID	    |serviceId	|String	  |path	  |O	|서비스 ID, URL PATH 내에 설정한{serviceId}|
|언어 코드	    |language	  |String	  |query	|X	|헬프센터 언어 코드(기본 값 : 기본 언어 코드)|
|카테고리 ID	  |categoryId	|Integer	|query	|X	|FAQ 카테고리 ID|
|키워드	        |query	    |String	  |query	|X	|검색 키워드(조회 범위: FAQ 제목, 내용)|
|정렬 필드  	  |sort	      |String	  |query	|X	|isTop, isRecommend, createdDt, updatedDt 필드로 정렬 가능하며, 여러 필드 정렬시 [,]로 분리. asc:오름차순; desc:내림차순|
|페이지	        |page	      |Integer	|query	|X  |페이지 번호(기본 값: 1)|
|페이지 당 건수	|pageSize	  |Integer	|query	|X	|페이지 당 데이터 건수(기본 값: 10건, MAX: 200)|

sort 파라미터의 형식 및 예시는 하기와 같습니다.

- 형식: 필드1:정렬,필드2:정렬,……
- 예시: isTop:desc,createdDt:asc
- 기본 정렬(카테고리 ID가 빈 값이 아닐 경우): isTop:desc,isRecommend:desc,updatedDt:desc
- 기본 정렬(카테고리 ID가 빈 값일 경우): isTop:desc,updatedDt:desc

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|----|-----------|------|
|result.contents	|helpDocId	  |Integer		|FAQ ID|
|	                |title	      |String		  |FAQ 제목|
|	                |content	    |String		  |FAQ 내용|
|	                |isRecommend	|Boolean		|카테고리 별 고정 여부(true: 고정; false: 고정 아님)|
|	                |isTop	      |Boolean		|메인 화면 고정 여부(true: 고정; false: 고정 아님)|
|	                |createdDt	  |Long		    |등록 시간|
|	                |updatedDt	  |Long		    |수정 시간|
|	                |categoryId	  |Integer		|FAQ 카테고리 ID|
|	                |categoryName	|String		  |카테고리 명칭, 요청 파라미터의 언어 코드에 대응되는 언어의 카테고리 명칭 노출|
|	                |isNew	      |String		  |FAQ NEW 표시(true: 노출시간(displayDt) 값이 오늘, false: 노출시간(displayDt) 값이 오늘 외|
|result	          |total	      |Integer		|총 건수|
|	                |pages	      |Integer		|총 페이지 수|
|	                |pageNum	    |Integer		|페이지|
|	                |pageSize	    |Integer		|페이지 당 건수|

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
                "helpDocId": 3414,	
                "title": "자주 묻는 질문 제목2",	
                "content": "자주 묻는 질문 내용2",	
                "isRecommend": false,	
                "isTop": true,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657265718000,	
                "updatedDt": 1657265718000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2551,	
                "categoryName": "유형1-1-2",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3413,	
                "title": "자주 묻는 질문 제목1",	
                "content": "자주 묻는 질문 내용1",	
                "isRecommend": true,	
                "isTop": true,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657265403000,	
                "updatedDt": 1657265403000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3423,	
                "title": "자주 묻는 질문 제목11",	
                "content": "자주 묻는 질문 내용11",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657266235000,	
                "updatedDt": 1657266235000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3422,	
                "title": "자주 묻는 질문 제목10",	
                "content": "자주 묻는 질문 내용10",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657266185000,	
                "updatedDt": 1657266196000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3421,	
                "title": "자주 묻는 질문 제목9",	
                "content": "자주 묻는 질문 내용9",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657266110000,	
                "updatedDt": 1657266110000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3420,	
                "title": "자주 묻는 질문 제목8",	
                "content": "자주 묻는 질문 내용8",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657266059000,	
                "updatedDt": 1657266059000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3419,	
                "title": "자주 묻는 질문 제목7",	
                "content": "자주 묻는 질문 내용7",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657266009000,	
                "updatedDt": 1657266009000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2550,	
                "categoryName": "유형1-1-1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3418,	
                "title": "자주 묻는 질문 제목6",	
                "content": "자주 묻는 질문 내용6",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657265956000,	
                "updatedDt": 1657265956000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2547,	
                "categoryName": "유형2",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3417,	
                "title": "자주 묻는 질문 제목5",	
                "content": "자주 묻는 질문 내용5",	
                "isRecommend": false,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657265902000,	
                "updatedDt": 1657265902000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2546,	
                "categoryName": "유형1",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            },	
            {	
                "helpDocId": 3416,	
                "title": "자주 묻는 질문 제목4",	
                "content": "자주 묻는 질문 내용4",	
                "isRecommend": true,	
                "isTop": false,	
                "readCnt": null,	
                "attachmentYn": null,	
                "createdDt": 1657265838000,	
                "updatedDt": 1657265838000,	
                "parentCategoryList": null,	
                "category": null,	
                "categoryId": 2549,	
                "categoryName": "유형1-2",	
                "categoryFullName": null,	
                "attachments": null,	
                "isNew": false	
            }	
        ],	
        "total": 11,	
        "pages": 2,	
        "pageNum": 1,	
        "pageSize": 10	
    }	
}	
```

### FAQ 상세
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/helpdoc/detail/{id}.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/helpdoc/detail/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|FAQ 상세 |HTTPS  |GET    |UTF-8|JSON    |FAQ ID를 통해 FAQ 내용 취득|필요 없음 |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형 |필수	|설명|
|----|------|-----------|---------|------|----|
|서비스 ID	|serviceId	|String	 |path	 |O	 |URL PATH 내에 설정한{serviceId}|
|FAQ ID	    |id	       |Integer	|path	  |O	|URL PATH 내에 설정한{id}|
|언어 코드	|language	  |String	 |query	 |X	 |서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|----------|--------|
|result.content	|helpDocId	                    |Integer		 |FAQ ID|
|	              |title	                        |String		   |FAQ 제목|
|	              |content	                      |String		   |FAQ 내용|
|               |isRecommend	                  |Boolean		 |추천|
|	              |isTop	                        |Boolean		 |상단 고정|
|	              |readCnt	                      |Integer		 |조회수|
|	              |attachmentYn	                  |Boolean		 |첨부파일 포함 여부|
|	              |createdDt	                    |Long	     	 |FAQ 등록 시간|
|	              |updatedDt	                    |Long		     |FAQ 수정 시간|
|	              |parentCategoryList	            |Array	  	 |상위 카테고리 정보|
|	              |parentCategoryList.categoryId	|Integer		 |카테고리 ID|
|	              |parentCategoryList.parent	    |Integer		 |상위 카테고리 ID|
|	              |parentCategoryList.name	      |String		   |카테고리 명|
|	              |parentCategoryList.level	      |Integer		 |카테고리 뎁스(0, 1, 2)|
|	              |parentCategoryList.path	      |String		   |카테고리 뎁스 경로(\\\\로 각 뎁스ID 연결)|
|	              |parentCategoryList.orderNo	    |Integer		 |카테고리 표시 순서 설정|
|	              |parentCategoryList.languages  	|Object		   |다국어 카테고리 명|
|	              |category	                      |Object		   |카테고리 정보|
|	              |category.categoryId			      |            |카테고리 ID|
|	              |category.parent			          |            |상위 카테고리 ID|
|	              |category.name			            |            |카테고리 명|
|	              |category.level			            |            |카테고리 뎁스(0, 1, 2)|
| 	            |category.languages			        |            |다국어 카테고리 명|
|	              |categoryId	                    |Integer		 |공지 카테고리 ID|
|	              |categoryName	                  |String		   |카테고리 명|
|	              |categoryFullName	              |String		   |카테고리 전체 경로 명|
|	              |attachments	                  |Array		   |첨부파일|
|	              |attachments.attachmentId	      |String		   |첨부파일 ID|
|	              |attachments.fileName	          |String		   |첨부파일 명|
|	              |attachments.contentType	      |String		   |첨부파일 유형|
|	              |attachments.size	              |Long		     |첨부파일 사이즈|
|        	      |isNew	                        |String		   |신규 공지 표시. true: 노출 시간(displayDt) 값이 오늘, false: 노출 시간(displayDt) 값이 오늘 외|

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
            "helpDocId": 3413,		
            "title": "자주 묻는 질문 제목1",		
            "content": "<p>자주 묻는 질문 내용1</p>",		
            "isRecommend": true,		
            "isTop": true,		
            "readCnt": 12,		
            "attachmentYn": "Y",		
            "createdDt": 1657265404000,		
            "updatedDt": 1657265404000,		
            "parentCategoryList": [		
                {		
                    "categoryId": 2546,		
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
                    "categoryId": 2548,		
                    "parent": 2546,		
                    "name": "유형1-1",		
                    "level": 2,		
                    "path": "\\2546\\",		
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
                    "categoryId": 2550,		
                    "parent": 2548,		
                    "name": "유형1-1-1",		
                    "level": 3,		
                    "path": "\\2546\\2548\\",		
                    "orderNo": 0,		
                    "languages": {		
                        "ko": "유형1-1-1",		
                        "th": "พิมพ์1-1-1",		
                        "ja": "タイプ1-1-1",		
                        "en": "Type1-1-1",		
                        "zh": "类型1-1-1"		
                    }		
                }		
            ],		
            "category": {		
                "categoryId": 2550,		
                "parent": 2548,		
                "name": "유형1-1-1",		
                "level": 3,		
                "languages": {		
                    "ko": "유형1-1-1",		
                    "th": "พิมพ์1-1-1",		
                    "ja": "タイプ1-1-1",		
                    "en": "Type1-1-1",		
                    "zh": "类型1-1-1"		
                }		
            },		
            "categoryId": 2550,		
            "categoryName": "유형1-1-1",		
            "categoryFullName": "유형1>유형1-1>유형1-1-1",		
            "attachments": [		
                {		
                    "attachmentId": "badf8fac176e42cc85e232e19759ad2f",		
                    "fileName": "nhn.png",		
                    "contentType": "image/png",		
                    "size": 9682		
                },		
                {		
                    "attachmentId": "d4f3667f13c14ddea57cd55b71df868c",		
                    "fileName": "logo_footer.png",		
                    "contentType": "image/png",		
                    "size": 1412		
                }		
            ],		
            "isNew": false		
        }		
    }		
}		
```

### FAQ 첨부파일 열기 및 다운로드
#### 인터페이스 설명
- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/helpdoc/attachments/{id}
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/helpdoc/attachments/{id}	
									
|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|FAQ 첨부파일 열기 및 다운로드 |HTTPS  |GET    |UTF-8|JSON    |FAQ 첨부파일 열기 및 다운로드|필요 없음   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|----|------|-----------|---------|-----|---|
|서비스 ID	          |serviceId	|String	|path   |O	    |URL PATH 내에 설정한{serviceId}|
|업로드 파일 ID	      |id	        |String  |path   |O     |업로드 파일 ID| 
|열람 방식	          |type	      |String	|query   |X     |기본 값: 열기(download: 다운로드, open: 열기)|

#### 결과 데이터
File