## Security > Security Advisor > 콘솔 사용 가이드

Security Advisor의 기능과 사용하는 방법을 설명합니다.

## 대시보드

Security Advisor 점검 항목에서 점검한 결과를 확인할 수 있습니다.
조직을 검사한 결과는 리전 선택과 관계 없이 모두 표시되며 프로젝트 자원은 선택된 리전에 생성된 자원을 점검한 결과를 표시합니다.

* **점검 결과 요약**은 알림 기준별로 점검된 항목의 개수를 표시합니다.
  - 대시보드에 설명되어 있는 **알림 기준**은 위험도 판단의 기본 수준입니다.
  개별 점검 항목의 알림 기준은 항목별로 다르게 적용되어 있습니다.
  - 선택 점검 결과의 탐지 리소스 중 점검 예외 설정된 리소스 합계를 예외에 표시합니다.
  - 자동 점검 설정은 설정 메뉴에서 설정한 점검 주기가 표시 됩니다.
* **점검 결과 목록 요약**은 **위험, 주의, 관심** 기준으로 탐지된 리소스가 존재하는 항목을 표시합니다.
  - 점검 결과가 **양호**인 항목은 표시 하지 않습니다.
  - 상세 보기 열의 **조회**를 클릭하면 점검 항목 페이지로 이동하여 상세 정보를 확인할 수 있습니다.
* **엑셀 저장**을 클릭하면 점검 결과를 엑셀 파일로 내려받을 수 있습니다.
  - 엑셀 파일에는 점검 항목에서 가장 마지막으로 선택 점검한 결과(점검 항목의 기본 정보와 탐지 리소스, 점검 시간)가 저장되어 있습니다.
  - 엑셀 파일에는 예외 리소스와 설정 정보는 포함되지 않습니다.
  - 서비스 활성화 이후 한번도 선택 점검을 진행하지 않아 점검 결과가 없을 경우 엑셀 파일을 다운로드할 수 있지만 파일은 열리지 않습니다.
![이미지3](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_03.png)


## 점검 항목

제공되는 항목 중 원하는 항목을 체크하여 점검을 실행하고 그 결과와 조치 가이드를 확인할 수 있습니다.
점검 결과의 상세 내용을 확인하고, 점검이 불필요한 항목을 예외 처리할 수 있습니다.
### 선택 점검
1. 점검할 리전을 선택합니다.
  (조직으로 구분된 항목은 모든 리전에 동일하게 설정되어 있으므로 리전을 변경해도 결과가 동일합니다.)
2. 점검할 항목을 체크한 뒤 **선택 점검**을 클릭합니다.
3. 점검이 완료되면 점검 항목별로 결과를 확인합니다.
4. 프로젝트로 구분된 항목은 리전을 변경하여 선택 점검합니다.
![이미지4](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_04.png)

### 기본 정보

* 점검 항목에 대한 설명을 확인할 수 있습니다.
* 탐지 리소스 개수, 예외 리소스 개수, 최종 점검일을 확인할 수 있습니다.
* 알림 기준을 확인하고 권장 조치를 참고하여 탐지된 리소스를 조치할 수 있습니다.
![이미지5](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_05.png)

### 탐지 리소스

* 점검 항목별 알림 기준에 따라 탐지된 리소스의 상세 정보를 확인할 수 있습니다.
* 탐지된 리소스 중 원하는 항목을 체크하여 **선택 예외**를 클릭하면 다음 점검 시 해당 리소스는 예외 처리됩니다.
![이미지6](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_06.png)
![이미지7](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_07.png)

### 예외 목록

* 점검 예외 처리된 항목을 확인할 수 있습니다.
* **변경**을 클릭하여 메모를 작성할 수 있습니다.
* 원하는 항목을 체크하여 **예외 해제**를 클릭하면 점검 대상에 포함시킬 수 있습니다.
![이미지10](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_11.png)

## 설정

자동 점검을 설정하여 원하는 시간에 주기적으로 점검하도록 설정할 수 있습니다.
이메일 주소를 입력하면 자동 점검 결과를 이메일 수신자에게 전달합니다. 자동 점검을 설정하더라도 이메일 주소를 설정하지 않을 경우 점검 결과는 콘솔에만 반영됩니다.
설정을 변경한 뒤 반드시 **저장**을 클릭해야 변경한 값이 적용됩니다.

### 관리자 설정

* 점검 결과를 수신할 관리자의 이메일 주소를 설정합니다. 점검 결과가 전달되므로 이메일 주소를 정확하게 입력하십시오.
* 이메일은 필수 입력값은 아닙니다.
![이미지8](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_08.png)
### 점검 설정
* 원하는 **점검 주기**를 설정하여 자동으로 점검되도록 설정할 수 있습니다. 점검된 결과는 자동으로 콘솔에 반영되며, 이메일 주소를 설정한 경우 이메일 수신자에게 결과가 발송됩니다.
* **자동 점검 항목**을 선택할 수 있습니다.
![이미지9](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_09.png)
