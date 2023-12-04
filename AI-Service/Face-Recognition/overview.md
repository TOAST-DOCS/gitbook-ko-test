## AI Service > Face Recognition > 개요

* NHN Cloud의 얼굴 인식 서비스는 머신러닝 기술로 양질의 얼굴 데이터셋을 학습하여 개발된 서비스입니다.
* 얼굴 감지 및 분석, 비교를 포함한 여러 기능을 제공하며 다양한 시나리오에서 신원 인증 기능을 지원합니다.
* 금융이나 의료, 커머스 등 얼굴 식별이 가능한 여러 온/오프라인 환경에서 세밀하고 개인화된 고객 맞춤형 서비스를 제공할 수 있습니다.

## 주요 기능

다음과 같은 기능을 제공합니다.

* **Face Detection & Analysis(얼굴 감지 및 분석)**
    * 입력 이미지에서 얼굴을 감지하는 기능입니다.
    * 감지한 얼굴의 속성을 분석하여 얼굴, 눈, 코, 입의 위치 정보와 신뢰도 값을 반환합니다.
* **Face Comparison(얼굴 비교)**
    * 입력 이미지에서 감지한 얼굴이 비교 대상 이미지에서 감지한 얼굴과 일치하는지 비교하는 기능입니다.
    * 입력 이미지가 다수의 얼굴을 포함하는 경우, 감지한 얼굴 중에서 가장 큰 얼굴과 비교 대상 이미지에서 감지한 각각의 얼굴을 비교해 유사도 값을 반환합니다.
* **Managing Group(그룹 관리)**
    * 얼굴을 등록하기 위한 그룹을 생성할 수 있으며, 생성한 그룹 리스트를 조회하거나 삭제할 수 있는 기능입니다.
    * 입력 이미지에서 감지한 얼굴을 그룹에 등록하거나 그룹에 등록한 얼굴을 조회 및 삭제할 수 있습니다.
* **Face Indexing & Searching(얼굴 검색)**
    * 사전에 얼굴 정보를 분석해서 저장해두고 있다가 Face ID나 이미지를 전달하여 얼굴을 검색하고 신원을 식별하는 기능입니다.
    * 분석한 얼굴 정보는 FaceI ID로 관리합니다
    * 이때, 입력한 값(Face ID나 이미지)과 일치하는 일련의 얼굴을 검색 결과로 반환하며 유사도 값이 높은 순서로 정렬합니다.
* **Face Verification(얼굴 검증)**
    * 사전에 등록된 특정 얼굴의 페이스 ID와 입력 이미지에서 감지한 얼굴을 비교하여 유사도 값을 반환하는 기능입니다.
    * 동일 얼굴인지 판단하는 유사도 기준값을 사용자가 직접 설정하여 일치 여부를 판단할 수 있습니다.
    * 높은 수준의 보안이 요구되는 경우 유사도 기준값을 상향하여 엄밀한 검증이 가능합니다.
* **Face Spoofing Detection(얼굴 스푸핑 감지)**
    * 얼굴 인식으로의 불법적 접근이나 스푸핑(얼굴 사진, 동영상 등의 얼굴 인식 왜곡 행위)을 방지하기 위한 감지 기능입니다.
    * 감지된 얼굴 이미지를 분석하여 얼굴의 스푸핑 여부를 반환합니다.
    * Face Recognition API(얼굴 감지/얼굴 등록/얼굴 비교/이미지로 얼굴 검색/얼굴 검증)에서도 얼굴 스푸핑 감지 기능을 사용할 수 있습니다.

## 서비스 대상

* 얼굴 인식 기술을 활용한 출입 관리 시스템 구축이 필요한 경우
* 방문객 모니터링이 필요한 경우
* 건설 현장 근로자의 위치를 확인하여 안전한 현장 환경을 구축하고자 하는 경우
* 얼굴 인식 기술을 활용한 결제 시스템 구축이 필요한 경우
* 사진 앨범에서 특정 얼굴이 포함된 사진을 찾고자 하는 경우
* 얼굴 이미지의 스푸핑 여부를 파악하고 싶을 경우


## 개인정보 처리에 대한 안내

- 얼굴 인식 서비스를 이용하는 과정에서 고객은 이용자의 개인정보 및 민감정보를 수집할 수 있습니다. 따라서 본 서비스를 이용하는 고객은 개인정보보호법에 따라 이용자에게 법적 고지사항을 알리고 동의를 받아야 합니다.
또한, 이 과정에서 고객과 NHN Cloud 간 개인정보 처리에 관한 업무 위수탁 관계가 발생할 수 있습니다. 위탁자의 지위에 있는 고객은 수탁사인 NHN Cloud와 별도 서면에 의한 위탁 계약을 체결할 수 있으며 고객이 운영하는 개인정보처리방침에 아래 내용을 참고하여 고지할 수 있습니다.

     \- 수탁 업체: 엔에이치엔클라우드 ㈜
     \- 위탁 업무의 내용: 얼굴 인식 서비스 제공 업무
 
 