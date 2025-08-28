# 클라우드 계정 설정
> [!NOTE]
> `Aria Automation` 에서 `admin/System Domain` 계정으로 수행

Aria Automation 에서 사용할 vCenter, NSX 등록 및 Aria Operation 연동을 위한 작업을 수행합니다.

<p align="center"><img src="images/aa-ca-01.png" width="75%" /><br/>< Assembler 선택 ></p>

<p align="center"><img src="images/aa-ca-02.png" width="75%" /><br/>< Infrastructure > Cloud Accounts 메뉴 선택 ></p>

<p align="center"><img src="images/aa-ca-03.png" width="75%" /><br/>< vCenter 등록 선택 ></p>

<p align="center"><img src="images/aa-ca-04.png" width="75%" /><br/>< vCenter 엔드포인트 등록 ></p>

> [!NOTE]
> `Name` 필드에 반드시 vCenter FQDN 이름을 등록

> [!CAUTION]
> `Allow provisioning to these datacenters` 에서 데이터센터 선택 후 `Create a cloud zone for the selected datacenters` 체크박스를 반드시 해제 하고 저장

<p align="center"><img src="images/aa-ca-05.png" width="75%" /><br/>< vCenter 등록 완료 ></p>

<p align="center"><img src="images/aa-ca-06.png" width="75%" /><br/>< NSX-T 관리자 등록 선택 ></p>

<p align="center"><img src="images/aa-ca-07.png" width="75%" /><br/>< NSX-T 엔드포인트 등록 ></p>

> [!NOTE]
> `Name` 필드에 반드시 NSX-T 관리자의 LoadBalancer FQDN 또는 Master 노드 FQDN 이름을 등록

> [!NOTE]
> `Associations` 에 등록한 vCenter 엔드포인트를 추가

<p align="center"><img src="images/aa-ca-08.png" width="75%" /><br/>< NSX-T 관리자 등록 완료 ></p>

<p align="center"><img src="images/aa-ca-09.png" width="75%" /><br/>< Infrastructure > Integration 메뉴 선택 ></p>

<p align="center"><img src="images/aa-ca-10.png" width="75%" /><br/>< VMware Aria Operations 등록 선택 ></p>

<p align="center"><img src="images/aa-ca-11.png" width="75%" /><br/>< VMware Aria Operations 엔드포인트 등록 ></p>

<p align="center"><img src="images/aa-ca-12.png" width="75%" /><br/>< VMware Aria Operations 등록 완료 ></p>
