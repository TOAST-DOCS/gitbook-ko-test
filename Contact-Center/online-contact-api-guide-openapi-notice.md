## Contact Center > Online Contact > API 가이드 > 공지사항

### 말머리 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/notice/categories.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/notice/categories.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|말머리 리스트|HTTPS  |GET  |UTF-8|JSON    |공지사항 말머리 리스트|필요 없음|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형	|필수 |설명|
|----|-----|------------|-----------|-----|---|
|서비스 ID	|serviceId	|String	|path	  |O	|URL PATH 내에 설정한{serviceId}|
|언어코드	|language	  |String	|query	|X	|서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|---------|--------|---------------|----|
|result.contents	|categoryId	|Integer		|말머리 ID|
|	                |parent	    |Integer		|상위 말머리 ID（고정 값: 0）|
|	                |name	      |String		  |말머리 명|
|	                |level	    |Integer		|뎁스（고정 값: 1）|
|	                |path	      |String		  |뎁스 경로（고정 값: "\\\\"）|
|	                |orderNo	  |Integer		|정렬 순서|
|	                |languages	|Object		  |말머리 다국어 명칭, 값(언어 코드: 대응되는 언어 코드 명칭)|

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
                "categoryId": 2543,	
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
                "categoryId": 2544,	
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
                "categoryId": 2545,	
                "parent": 0,	
                "name": "유형3",	
                "level": 1,	
                "path": "\\",	
                "orderNo": 2,	
                "languages": {	
                    "ko": "유형3",	
                    "th": "พิมพ์3",	
                    "ja": "タイプ3",	
                    "en": "Type3",	
                    "zh": "类型3"	
                }	
            }	
        ]	
    }	
}	
```

### 태그 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/notice/tags.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/notice/tags.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|태그 리스트  |HTTPS  |GET    |UTF-8|JSON    |공지사항 태그 리스트|필요 없음|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-----|-----|------------|--------|----|----|
|서비스 ID	|serviceId	|String	|path  |O	|URL PATH 내에 설정한{serviceId}|
|태그 키워드 |language	|String	|query |X	|태그 검색 문구|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|--------|---------|------------|--------|
|result.contents	|tagId	|Integer		|태그 ID|
|	                |tag	  |String		  |태그 명칭|
|	                |languages	|Object		|태그 다국어 명칭, 값(언어 코드: 대응되는 언어 코드 명칭)|

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
                "tagId": 391,	
                "tag": "태그1",	
                "languages": {	
                    "ko": "태그1",	
                    "th": "แท็ก1",	
                    "ja": "タグ1",	
                    "en": "Tag1",	
                    "zh": "标签1"	
                }	
            },	
            {	
                "tagId": 392,	
                "tag": "태그2",	
                "languages": {	
                    "ko": "태그2",	
                    "th": "แท็ก2",	
                    "ja": "タグ2",	
                    "en": "Tag2",	
                    "zh": "标签2"	
                }	
            }	
        ]	
    }	
}	
```

### 공지사항 리스트
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/notice/list.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/notice/list.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|공지사항 리스트|HTTPS  |GET    |UTF-8|JSON    |헬프센터 공지사항 리스트|공통 인증   |

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-----|-----|------------|--------|----|----|
|서비스 ID	       |serviceId	  |String	    |path	  |O	|URL PATH 내에 설정한{serviceId}|
|언어코드	         |language	   |String	  |query	|X	|서비스 헬프센터 기본 언어 코드|
|카테고리 ID	     |categoryId	 |Integer	  |query	|X	|카테고리 ID|
|태그 ID	         |tagId	       |Integer	  |query	|X	|태그 ID|
|키워드 검색	      |query	     |String	  |query	 |X	 |키워드 검색(검색 범위: 제목, 내용)|
|정렬 순서	        |sort	       |String	  |query	 |X	 |isTop, createdDt, updatedDt, displayDt 필드로 정렬 가능하며, 여러 필드 정렬시 [,]로 분리. asc:오름차순; desc:내림차순|
|페이지  	          |page   	   |Integer	  |query	 |X	 |기본 값: 1|
|1페이지 노출 건수	 |pageSize	  |Integer	 |query	  |X	|기본 값: 10; max=200|

sort 파라미터의 형식 및 예시는 하기와 같습니다.

- 형식: 필드1:정렬,필드2:정렬,……
- 예시: isTop:desc,createdDt:asc
- 기본 정렬: isTop:desc,displayDt:desc,updatedDt:desc

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|----|-----|------------|---|
|result.contents	|noticeId	    |Integer		|공지사항 ID|
|	                |categoryId	  |Integer		|공지사항 카테고리 ID|
|	                |isTop	      |Boolean		|상단 고정 표기 (true: yes; false: no)|
|	                |title	      |String		  |공지사항 제목|
|	                |content	    |String		  |공지사항 내용|
|	                |displayDt	  |String		  |출력 시간(yyyyMMddHHmmss)|
|	                |updatedDt	  |Long		    |수정 시간|
|	                |categoryName	|String		  |카테고리 명|
|	                |tagStr	      |Integer		|태그 명|
|	                |isNew	      |String		  |신규 공지사항 표시. true: 출력 시간(displayDt) 값이 오늘, false: 출력 시간(displayDt) 값이 오늘 외|
|result   	      |total	      |Integer		|총 건수|
|	                |pages	      |Integer		|총 페이지 수|
|	                |pageNum	    |Integer		|페이지|
|	                |pageSize	    |Integer		|페이지 당 노출 건수|

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
                "noticeId": 1241,	
                "categoryId": 2543,	
                "isTop": true,	
                "title": "공지제목7",	
                "content": "공지내용7",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657243026000,	
                "categoryName": "유형1",	
                "tagStr": "태그2",	
                "isNew": false	
            },	
            {	
                "noticeId": 1246,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목11",	
                "content": "공지내용11",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657243165000,	
                "categoryName": "유형1",	
                "tagStr": "태그1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1245,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목10",	
                "content": "공지내용10",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657243148000,	
                "categoryName": "유형1",	
                "tagStr": "태그1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1244,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목9",	
                "content": "공지내용9",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657243129000,	
                "categoryName": "유형1",	
                "tagStr": "태그1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1243,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목8",	
                "content": "공지내용8",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657243106000,	
                "categoryName": "유형1",	
                "tagStr": "태그1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1240,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목6",	
                "content": "공지내용6",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657242949000,	
                "categoryName": "유형1",	
                "tagStr": "태그2",	
                "isNew": false	
            },	
            {	
                "noticeId": 1239,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목5",	
                "content": "공지내용5",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657242735000,	
                "categoryName": "유형1",	
                "tagStr": "태그1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1238,	
                "categoryId": 2543,	
                "isTop": false,	
                "title": "공지제목4",	
                "content": "공지내용4",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657242576000,	
                "categoryName": "유형1",	
                "isNew": false	
            },	
            {	
                "noticeId": 1237,	
                "categoryId": 2545,	
                "isTop": false,	
                "title": "공지제목3",	
                "content": "공지내용3",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657242501000,	
                "categoryName": "유형3",	
                "tagStr": "태그1,태그2",	
                "isNew": false	
            },	
            {	
                "noticeId": 1236,	
                "categoryId": 2544,	
                "isTop": false,	
                "title": "공지제목2",	
                "content": "공지내용2",	
                "displayDt": "2022.07.08",	
                "updatedDt": 1657242420000,	
                "categoryName": "유형2",	
                "tagStr": "태그2",	
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

### 공지사항 상세
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/notice/detail/{id}.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/notice/detail/{id}.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|공지사항 상세|HTTPS  |GET    |UTF-8|JSON    |공지사항 ID를 통해 공지사항 내용 취득|필요 없음|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-----|-----|------------|--------|----|----|
|서비스 ID	  |serviceId	|String	  |path	  |O	|URL PATH 내에 설정한{serviceId}|
|공지사항 ID	|id	        |Integer	|path	  |O	|공지사항 ID|
|언어 코드	  |language	  |String	  |query	|X	|서비스 헬프센터 기본 언어 코드|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|-----|-----------|----|
|result.content	|noticeId	                |Integer	|공지사항 ID|
|	              |categoryId	              |Integer	|말머리 ID|
|	              |isTop	                  |Boolean	|상단고정 표기|
|	              |title	                  |String		|공지사항 제목|
|	              |content	                |String		|공지사항 내용|
|	              |displayDt	              |String		|출력 시간(yyyyMMddHHmmss)|
|	              |attachmentYn	            |Boolean	|첨부파일 포함 여부，값(true: 포함; false: 포함하지 않음)|
|	              |readCnt	                |Integer	|조회 횟수|
|	              |updatedDt	              |Long		  |공지사항 수정 시간|
|	              |attachments	            |Array		|공지사항 첨부|
|	              |attachments.attachmentId	|String		|첨부파일 ID|
|	              |attachments.fileName	    |String		|첨부파일 명|
|	              |attachments.contentType	|String		|첨부파일 유형|
|	              |attachments.size	        |Long		  |첨부파일 사이즈|
|	              |tags	                    |Array		|공지사항 태그|
|	              |tags.tagId	              |Integer	|태그 ID|
|	              |tags.tag	                |String		|태그 명칭|
|               |categoryName	            |String		|말머리 명칭|
|	              |isNew	                  |String		|신규 공지사항 표시. true: 노출 시간(displayDt)이 오늘, false: 노출 시간(displayDt)이 오늘 외|

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
            "noticeId": 1240,	
            "categoryId": 2543,	
            "isTop": true,	
            "title": "공지제목6",	
            "content": "<p>공지내용6</p>",	
            "displayDt": "2022.07.08",	
            "attachmentYn": "Y",	
            "readCnt": 5,	
            "updatedDt": 1658114209000,	
            "attachments": [	
                {	
                    "attachmentId": "42fb4c8801ed4c278475f70f531b8c92",	
                    "fileName": "logo_footer.png",	
                    "contentType": "image/png",	
                    "size": 1412	
                }	
            ],	
            "tags": [	
                {	
                    "tagId": 391,	
                    "tag": "태그1"	
                },	
                {	
                    "tagId": 392,	
                    "tag": "태그2"	
                }	
            ],	
            "categoryName": "유형1",	
            "isNew": false	
        }	
    }	
}	
```

### 공지사항 첨부파일 열기 및 다운로드
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/notice/attachments/{id}	
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/notice/attachments/{id}		

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|--------|
|공지사항 첨부파일 열기 및 다운로드|HTTPS  |GET    |UTF-8|JSON    |공지사항 첨부파일 열기/다운로드|필요 없음|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|----|-----|------------|---------|-----|----|
|서비스 ID	    |serviceId	|String	  |path	 |O	|URL PATH 내에 설정한{serviceId}|
|업로드 파일 ID	|id	         |String	|path	  |O	|업로드 파일 ID|
|열람 방식	    |type	       |String	|query	|X	|기본 값:열기(download: 다운로드, open: 열기）|

#### 결과 데이터
File

