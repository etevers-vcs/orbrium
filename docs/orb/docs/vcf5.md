# VCF5 환경 사전 준비

## 1. 고유 키 확인

> [!NOTE]
> `Aria Automation` 에서 `admin/System Domain` 계정으로 수행

<p align="center"><img src="images/aa-key-01.png" width="75%" /><br/>< Orchestrator 서비스 모듈 선택 ></p>

<p align="center"><img src="images/aa-key-02.png" width="75%" /><br/>< Get Package Keys 워크플로우 실행 ></p>

`Orchestrator` > `Workflows` > `BVP` > `Package` >`Get Package Keys` 워크플로우를 실행 (`RUN`) 합니다. 만약 화면 구성이 위 그림과 같이 Tree View 형태가 아니라면, 우상단에 있는 화면 표시 설정을 조정하여 Tree View 형태로 바꿀 수 있습니다. 실행 결과는 다음과 같이 나타납니다.

<p align="center"><img src="images/aa-key-03.png" width="75%" /><br/>< 워크플로우 결과 화면 ></p>

워크플로우가 정상으로 수행되었다면 `Completed` 상태가 되며, 실행 결과 하단의 `Variables` 탭으로 이동하면 `accessKey` 와 `secretKey` 를 확인 할 수 있습니다.
이 키는 오브리움 한 사이트(=회사, =Org) 단위로 고유한 값이어야 합니다.
만약 오브리움에 여러 Aria Automation(=Multi Region)을 연결해야 한다면, 각 Aria Automation의 `accessKey` 와 `secretKey` 를 동일하게 수정해 주어야 합니다.
`accessKey` 와 `secretKey` 는 오브리움 배포 전 언제든지 `Orchestrator` > `Configuration` > `BVP` > `Endpoint` > `Orbrium` > `data` 항목에서 수정 가능합니다.

확인한 `accessKey` 와 `secretKey` 를 오브리움 설치를 위해 문서 편집기에 임시로 복사해 놓습니다.
`accessKey`와 `secretKey`는 영속적으로 유지되어야 하며 변경 불가능 하기 때문에, 반드시 보안을 지켜 사용해야 합니다.

> [!CAUTION]
> `accessKey` 와 `secretKey` 를 절대 유출하지 마세요.

> [!WARNING]
> `accessKey` 와 `secretKey` 변경은 사전 설계작업을 통해 에티버스와 함께 결정합니다. key를 구성하는 요건에 대한 사전 검증이 필요합니다.

## 2. 계정 정보 연동

> [!NOTE]
> `VMware Identity Manager` 에서 `admin/System Domain` 계정으로 수행

<p align="center"><img src="images/idm-02.png" width="75%" /><br/>< 관리 콘솔로 이동 ></p>

<p align="center"><img src="images/idm-03.png" width="75%" /><br/>< 디렉토리 추가 ></p>

> [!NOTE]
> 디렉토리는 회사 환경 및 아키텍처 구성에 따라 다양한 방법 또는 제품이 사용 될 수 있습니다.\
> 예제의 경우는 에티버스 내부의 테스트용 Microsoft Active Directory (AD) 를 연동하는 경우에 대한 샘플 예제 입니다.

> [!NOTE]
> 고객사 환경 계정 정보 연동은 에티버스에서 공식 지원합니다.
> 다만 무상 지원의 경우 표준 AD/LDAP 환경 또는 표준 OAuth2, SAML2.0 환경으로 제한하며, 그 이외의 고객사 고유의 계정시스템이나 SaaS형 솔루션에 대한 연동은 상황에 따라 비용이 발생하는 프로젝트로 수행하여야 합니다.
> 전체적인 클라우드 계정 및 도메인 영역 설계에 대한 사전 아키텍처 지원은 EVCS 가이드를 참조하면 됩니다.
> EVCS에 따른 고객사 환경 사전설계에 대한 감수 작업을 에티버스에서 수행합니다.

<p align="center"><img src="images/idm-04.png" width="75%" /><br/>< Active Directory 추가 ></p>

<p align="center"><img src="images/idm-05.png" width="75%" /><br/>< 디렉토리 연동 정보 입력 ></p>

<p align="center"><img src="images/idm-06.png" width="75%" /><br/>< 도메인 확인 ></p>

<p align="center"><img src="images/idm-07.png" width="75%" /><br/>< 사용자 특성 정보 매핑 설정 ></p>

<p align="center"><img src="images/idm-08.png" width="75%" /><br/>< 그룹 동기화 설정 ></p>

<p align="center"><img src="images/idm-09.png" width="75%" /><br/>< 사용자 동기화 설정 ></p>

<p align="center"><img src="images/idm-10.png" width="75%" /><br/>< 계정 동기화 검토 및 동기화 수행 ></p>

<p align="center"><img src="images/idm-15.png" width="75%" /><br/>< 계정 연동 확인 ></p>

사용자 및 그룹 으로 이동하여 Active Directory에 있는 정보가 정상적으로 동기화 되었는지 확인합니다.

> [!NOTE]
> 계정 정보 연동 후 특정 사용자 또는 그룹에게 권한 할당 작업 등을 수행 할 수도 있습니다.
> Aria 환경에 대한 권환관리를 위해 `admin` 계정을 직접 사용하여 조정 하는 것보다 특정 사용자 또는 그룹을 관리자 권한으로 만든 후, 작업에 대한 감사를 수행 할 수 있게 만드는 것이 안정적이고 보안적으로 우수한 권한 관리 방법입니다.
