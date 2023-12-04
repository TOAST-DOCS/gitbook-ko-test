## Network > VPN Gateway(Site-to-Site VPN) > 개요

VPC와 고객의 온프레미스 네트워크 사이에 암호화된 네트워크 연결을 할 수 있는 기능을 제공합니다.

## 개념

* 로컬 게이트웨이: NHN Cloud에서 VPN 터널 구성에 할당되는 리소스입니다.
* 리모트 게이트웨이: 온프레미스 측에서 VPN 터널 구성에 할당되는 리소스입니다.
* VPN 터널: 리모트 게이트웨이와 로컬 게이트웨이 사이에 구성되는 암호화된 링크입니다.

## 주요 기능

* VPC와 고객의 온프레미스 네트워크 사이에 암호화된 네트워크 연결을 할 수 있습니다.
* 대역폭(outbound 기준 보장)은 20M, 50M, 100M, 1G 중에서 선택할 수 있습니다.
* 암호화 알고리즘은 AES, DES, 3DES 중에서 선택이 가능합니다.
* 무결성 알고리즘은 MD5, SHA1, SHA256 중에서 선택이 가능합니다.
* 네트워크 ACL을 적용할 수 있습니다.
* 현재는 한국(평촌) 리전에만 제공됩니다. 점차 다른 리전도 지원할 예정입니다.

## 제한 사항

* VPN 연결에는 IPv6 트래픽이 지원되지 않습니다. IPv4 트래픽만 지원됩니다.
* VPC를 온프레미스 네트워크에 연결하는 경우 서로 네트워크 주소가 겹치지 않는 대역을 사용해야 합니다.
* VPC 단위로 VPN Gateway를 생성하며, 사용할 대역폭을 정할 수 있습니다. 하나의 VPN Gateway에 속한 VPN 연결은 모두 같은 대역폭을 이용합니다. 예를 들어 최초 VPN 연결을 20Mbps로 생성을 했다면 해당 VPC에서 이후 추가로 생성하는 VPN 연결은 모두 20Mbps 대역폭을 사용하게 됩니다. 다른 대역폭을 사용하려면 다른 VPC에서 최초 VPN 연결을 만들 때 원하는 대역폭(20M, 50M, 100M, 1G 중 선택)을 지정해서 생성할 수 있습니다.
* VPN Gateway는 각 VPC마다 한개씩 생성할 수 있습니다.
* 각 VPN Gateway당 최대 연결은 10개입니다.
* VPN과 연결된 VPC에서는 피어링을 사용해 다른 네트워크에 접근하거나, 기타 Gateway를 통해서 다른 네트워크 혹은 서비스에 접근하는 것을 지원하지 않습니다.