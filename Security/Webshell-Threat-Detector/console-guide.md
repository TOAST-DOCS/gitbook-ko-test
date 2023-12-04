## Security > Webshell Threat Detector > 콘솔 사용 가이드

여기에서는 점검 에이전트 활성화 절차를 설명합니다. 

## 에이전트 활성화 절차

인스턴스 OS를 선택하여 에이전트 설치 스크립트를 불러옵니다.

![WebshellThreatDetector_01_20221129.png](https://static.toastoven.net/prod_webshellthreatdetector/WebshellThreatDetector_01_20221129.png)

### Linux 계열 에이전트

1. 설치 스크립트를 복사하려면 **클립보드로 복사**를 클릭합니다.

2. 설치 대상 인스턴스 터미널에 접속합니다.

3. 관리자 권한으로 에이전트 스크립트를 생성하고 실행합니다.

* root 권한을 얻습니다.
* vi 편집기 등으로 스크립트를 생성합니다.
* 생성한 스크립트 파일의 권한을 변경합니다.
* 파일을 실행합니다.
```
[root@centos7 ~]# cd ~
[root@centos7 ~]# sudo su
[root@centos7 ~]# vi installer.sh
[root@centos7 ~]# chmod 744 installer.sh
[root@centos7 ~]# ./installer.sh
Configure the work directory..
Configure the data directory..
Install Finished!
```
## 에이전트 비활성화 절차

1. 삭제 스크립트를 복사합니다.

```
pkill pfcont && pkill pfmont && pkill pfrmont && pkill pfinstor && pkill pfsder && pkill acontroller && rm -rf /nwtd
```

2. 삭제 대상 인스턴스 터미널에 접속합니다.

3. 관리자 권한으로 삭제 스크립트를 실행합니다.

* Webshell Threat Detector 프로세스를 종료합니다.
* Webshell Threat Detector 파일을 삭제합니다.

4. 정상적으로 삭제되었음을 확인하고 싶다면, /nwtd 디렉터리가 존재하는지 확인합니다.

## 운영 문의

### 문의 대상

1. 에이전트 실행 실패 문의

2. 점검 결과에 대한 오용 탐지 신고

### 문의 방법

1. 문의 방법: **고객 센터 > 1:1 문의**

2. 대응 시간: 평일 09:00~18:00
