## Game > Launching > 개요 

모바일 앱을 실행하려면 서버 정보, 공지 사항 URL, 다운로드 URL 등 다양한 정보가 필요합니다. 그리고 이러한 모바일 앱 관련 정보가 변경되면 모바일 앱을 다시 배포해야 합니다.  Launching 서비스를 사용하면 모바일 앱을 처음 실행할 때 필요한 정보를 실시간으로 반영할 수 있어, 앱 정보가 변경되어도 다시 배포하지 않고 운영할 수 있습니다.

## 주요 기능

Launching 서비스에서는 다음과 같은 기능을 제공합니다.

* **동적으로 변경 가능한 서비스 정보를 서버나 모바일 앱 패치 없이 변경 가능**
서비스 모바일 앱을 처음 실행할 때 필요한 서버 정보, CDN 정보, 점검 상태 등의 변경 가능한 정보를 Launching에서 관리하면, 이러한 정보가 변경될 때 서버나 모바일 앱의 패치 작업이 필요 없습니다.

* **새로운 모바일 앱 버전이 출시되어도 이전 버전 관리 가능**
서비스 모바일 앱의 새로운 버전이 출시되면 이전 버전에 대한 업그레이드 알림, 강제 업데이트 수행 및 접속 불가 등의 동작을 설정할 수 있습니다.

* **특정 단말기나 OS 버전에 따른 서비스 접근 제한 가능**
특정 단말기 또는 iOS/Android 버전 업그레이드에 서비스 장애가 발생했을 때, 서버 및 모바일 앱 패치 없이 특정 단말기의 서비스를 제한할 수 있습니다.

* **사용자가 설정한 시간 동안 모바일 앱에 메시지 공지 가능**
사용자가 설정한 시간 동안에만 점검 일정 및 이벤트 등을 공지할 수 있으며, 서비스 점검 중에는 서비스를 중단하고 점검 메시지를 공지할 수 있습니다.

## 서비스 용어

Launching 서비스에서 사용하는 용어는 다음과 같습니다.

| 용어  | 설명                                                                    |
| --- | --------------------------------------------------------------------- |
| 론칭 | 서비스 단말기에서 앱을 구동할 때 필요한 초기 정보.                                       |
| 폴더  | 론칭 정보는 트리(tree) 구조로 구성되는데, 이때 중간 노드를 '폴더'라고 함. 폴더는 또 다른 폴더나 키를 가질 수 있음. |
| 키 KEY | 트리 구조의 최하단 단말 노드로, 값(value)을 가짐.                                     |
| 서브 키 Sub Key | 전체 론칭 정보에서 일부 데이터만을 얻고자 할 때 사용하는 키. 'launching.'으로 시작하며, '.'로 조합됨. |
| 키 패턴 Key Pattern | JSON 형식 설정 정보 루트의 상대적인 키. '$.'로 시작하며, '.'로 조합됨. |

## 서비스 흐름

![[그림 1 Launching 서비스 활성화]](http://static.toastoven.net/prod_launching/21.07.13/ko/overview_serviceflow.png)