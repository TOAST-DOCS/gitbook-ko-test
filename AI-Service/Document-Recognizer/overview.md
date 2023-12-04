## AI Service > Document Recognizer > 개요

Document Recognizer 서비스는 NHN Cloud의 OCR(광학 문자 인식) 기술을 통해 사업자등록증, 신용카드, 신분증의 문자 영역을 인식하고 영역별 문자를 추출하는 기능을 제공합니다. 
인식된 문서를 DB화하거나 문서 처리 자동화를 구현하는 고객사에서 활용할 수 있습니다. 

## 사업자등록증 분석

### 주요 기능

* **사업자등록증 문자 영역 인식**
	* 사업자등록증의 문자 영역(bounding box)을 인식하고, 해당 영역의 좌표를 제공합니다.
	
* **사업자등록증 주요 데이터 추출 및 분석**
    * 사업자등록증 분류(개인/법인)에 따른 주요 데이터는 Key/Value 한 쌍으로 분석되며, 이에 대한 신뢰값(confidence)을 제공합니다.

* **분석 결과 다운로드**
	* 사업자등록증 이미지 파일에서 추출한 결과를 Excel 및 JSON 파일로 다운로드할 수 있습니다.

### 입력 이미지 가이드

보다 정확한 사업자등록증 분석을 위해 아래의 가이드를 참고하세요.

* 파일 권장 사항
    * .pdf, .jpeg, .png 형식의 사업자등록증 이미지 분석 기능을 지원합니다. 
    * 최대 용량: 5MB
    * 권장 해상도: 1280 x 720 이상
* PDF의 경우 단일 페이지에 대한 분석 결과만 제공합니다. (여러 페이지인 경우 첫 페이지에 대한 분석 결과가 제공됩니다.)
* 평평한 곳에서 최대한 바르게 펴진 상태로 촬영된 이미지를 사용하세요.
* 사각 형태의 가득 찬 이미지로 인식하세요.
* 카메라 플래시 등으로 인한 빛 반사나 그늘로 인해 글자가 잘 안 보이는 경우 정확한 Key/Value 추출이 어려울 수 있습니다.
* 흑백/컬러 이미지에 대해 결과 분석이 가능하지만, 정확한 분석을 위해서 컬러 이미지를 권장합니다.
* 사업자등록증은 한국어에 한해 분석 결과를 제공합니다.

## 신용카드 분석

### 주요 기능

* **신용카드 문자 영역 인식**
	* 신용카드 이미지의 카드 번호, 유효 기간 문자 영역(bounding box)을 인식하고, 해당 영역의 좌표를 제공합니다.
	
* **신용카드 주요 데이터 추출 및 분석**
    * 신용카드 이미지의 카드 번호, 유효 기간 정보와 이에 대한 신뢰값(confidence)을 제공합니다.

* **분석 결과 다운로드**
	* 신용카드 이미지 파일에서 추출한 결과를 JSON 파일로 다운로드할 수 있습니다.

### 입력 이미지 가이드

보다 정확한 신용카드 분석을 위해 아래의 가이드를 참고하세요.

* 파일 권장 사항
    * 파일 형식: .jpeg, .png 형식의 이미지 분석 기능을 지원합니다.
    * 최대 용량: 5MB
    * 권장 해상도: 760 x 480
* 평평한 곳에서 최대한 바르게 펴진 상태로 촬영된 이미지를 사용하세요.
* 사각 형태의 가득 찬 이미지로 인식하세요.
* 카메라 플래시 등으로 인한 빛 반사나 그늘로 인해 글자가 잘 안 보이는 경우 정확한 Key/Value 추출이 어려울 수 있습니다.
* 흑백/컬러 이미지에 대해 결과 분석이 가능하지만, 정확한 분석을 위해서 컬러 이미지를 권장합니다.
* 세로 방향의 카드인 경우, 세로 카드의 카드 번호와 유효 기간이 정방향인 이미지로 인식하세요.
* 신용카드 분석 이미지 예시

![Image Example](http://static.toastoven.net/prod_document_ocr/DocumentRecognizer_ex_img.png)

## 신분증 분석

### 주요 기능

* **신분증 문자 영역 인식**
	* 신분증의 문자 영역(bounding box)을 인식하고, 해당 영역의 좌표를 제공합니다.

* **신분증 주요 데이터 추출 및 분석**
    * 신분증의 종류(주민등록증/운전면허증)에 따른 주요 데이터는 Key/Value 한 쌍으로 분석되며, 이에 대한 신뢰값(confidence)을 제공합니다.

* **신분증 진위 확인**
    * 신분증 이미지 파일에서 추출한 결과를 바탕으로 신분증의 진위를 확인할 수 있습니다.

* **분석 결과 다운로드**
	* 신분증 이미지 파일에서 추출한 결과를 JSON 파일로 다운로드할 수 있습니다.

### 입력 이미지 가이드

보다 정확한 신분증 분석을 위해 아래의 가이드를 참고하세요.

* 파일 권장 사항
    * 파일 형식: .jpeg, .png 형식의 이미지 분석 기능을 지원합니다.
    * 최대 용량: 5MB
    * 권장 해상도: 760x480
* 이미지 권장 사항
    * 평평한 곳에서 최대한 바르게 펴진 상태로 촬영된 이미지를 사용하세요.
    * 사각 형태의 가득 찬 이미지로 인식하세요.
    * 카메라 플래시 등으로 인한 빛 반사나 그늘로 인해 글자가 잘 안 보이는 경우 정확한 Key/Value 추출이 어려울 수 있습니다.
    * 흑백/컬러 이미지에 대해 결과 분석이 가능하지만, 정확한 분석을 위해서 컬러 이미지를 권장합니다.
    * 신분증(주민등록증/운전면허증)은 한국어에 한해 분석 결과를 제공합니다.

## 서비스 대상
* 문서(사업자등록증, 신용카드, 신분증)를 자동으로 고객사 시스템에 등록하는 경우
* 문서 처리 자동화를 구현하는 경우
* 회계/재무 관리 자동화 솔루션을 구축하는 경우

## 개인정보 처리에 대한 안내
* Document Recognizer 서비스를 이용하는 과정에서 고객은 이용자의 개인정보 및 고유식별정보를 수집할 수 있습니다. 따라서 본 서비스를 이용하는 고객은 개인정보보호법에 따라 이용자에게 법적 고지사항을 알리고 동의를 받아야 합니다. 또한, 이 과정에서 고객과 NHN Cloud 간 개인정보 처리에 관한 업무 위수탁 관계가 발생할 수 있습니다. 위탁자의 지위에 있는 고객은 수탁사인 NHN Cloud와 별도 서면에 의한 위탁 계약을 체결할 수 있으며 고객이 운영하는 개인정보처리방침에 아래 내용을 참고하여 고지할 수 있습니다.
    - 수탁 업체: 엔에이치엔클라우드㈜
    - 위탁 업무의 내용: Document Recognizer 서비스 제공 업무

## 기술적/관리적 수준에 대한 합의서
* 고객은 Document Recognizer 서비스를 이용하는 과정에서 수집/이용하는 정보의 민감성을 고려하여 기술적, 관리적 보호조치를 충실히 이행하여야 합니다.
* 고객은 Document Recognizer 서비스를 통하여 인식된 정보를 전달받기 위하여 Document Recognizer 서비스 이용 개시 전 통신구간 암호화를 완료하여야 합니다.
* 고객은 Document Recognizer 서비스에 인식 요청을 하는 원본 데이터는 안전한 장소에 저장되어야 하며, 외부에 노출된 URL로는 접근할 수 없어야 합니다.
* 고객은 Document Recognizer 서비스에서 안전한 인식결과 데이터를 제공하기 위해서 권장하는 전송 방식(전용선, IPSecVPN 등)을 채택해야 합니다.
* 고객은 Document Recognizer 서비스를 통하여 인식된 정보를 저장/보관/관리하는 데 있어서 개인정보 보호법 등 관련 법령을 준수하여야 합니다.
* 회사는 고객이 위에서 정한 기술적, 관리적 조치를 모두 갖추고 있는지 확인이 필요한 경우 고객에게 증빙을 요청할 수 있습니다.
* 위와 같은 사항은 Document Recognizer 서비스를 통하여 고객이 수집/이용하는 정보가 중요한 정보에 해당하기에 고객에게 요청하는 사항입니다.<br>당사는 고객의 요청에 따라 수탁자로서 위탁 받은 범위 내에서 정보를 처리하며, 고객은 정보처리의 주체로서 위 사항의 이행을 보증하고 위반으로 인하여 발생하는 정보주체, 규제기관 등에 대한 모든 책임을 부담하는 것을 확인합니다.