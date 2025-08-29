# Orchestrator 설정
Automation Orchestrator 사용에서는 Automation Orchestrator 클라이언트의 워크플로 자동화 특성 및 기능에 대한 정보를 제공합니다.

<p align="center"><img src="images/aa-o-01.png" width="75%" /><br/>< Orchestrator 선택 ></p>
  
## Automation Orchestrator 사용자 인터페이스
Automation Orchestrator 클라이언트를 사용하여 Automation Orchestrator 서비스 및 개체를 관리합니다.
- 대시보드:	Automation Orchestrator 클라이언트 대시보드 및 프로파일링 기능을 사용하여 Automation Orchestrator 환경 및 워크플로에 대한 유용한 메트릭 데이터를 수집합니다.
- 워크플로:	워크플로를 생성, 편집, 스케줄링, 실행 및 삭제합니다.
- 작업:	작업을 생성, 편집 및 삭제합니다. 작업 편집기는 Automation Orchestrator API 탐색기에 포함된 일반 스크립트 요소에 대한 자동 완성을 지원합니다.
- 정책:	정책을 생성, 편집, 실행 및 삭제합니다.
- 패키지:	Automation Orchestrator 개체가 포함된 패키지를 생성하고, 삭제하고, 내보내고, 가져옵니다.
- 구성:	구성 요소를 생성, 실행 및 삭제합니다.
- 리소스:	리소스 요소를 내보내고, 가져오고, 업데이트합니다.
  
<p align="center"><img src="images/aa-o-02.png" width="75%" /><br/>< Orchestrator 메인 화면 ></p>

### Broadcom Value Pack 패키지 설치


#### 1. 패키지 파일 가져오기

`Assets` > `Packages` > `IMPORT` 선택하여 다운받아놓은 패키지 파일을 가져옵니다.([BVP: Broadcom Value Pack > 바이너리 패키지 다운로드](https://github.com/etevers-vcs/orbrium/raw/refs/heads/main/files/broadcom-value-pack/com.bvp.package))

<p align="center"><img src="images/aa-o-03.png" width="75%" /><br/>< Assets > 패키지 목록 확인 ></p>

<p align="center"><img src="images/aa-o-04.png" width="75%" /><br/>< 패키지 가져오기 ></p>

<p align="center"><img src="images/aa-o-05.png" width="75%" /><br/>< 패키지 파일 상세 내용 확인 ></p>

<p align="center"><img src="images/aa-o-06.png" width="75%" /><br/>< 패키지 파일 IMPORT 선택 ></p>

#### 2. 패키지 파일 설치

`Library` > `Workflows` > `BVP` > `Package` > `Install Value Pack` 을 실행시켜 오브리움을 위한 요소들을 설치합니다.

<p align="center"><img src="images/aa-o-07.png" width="75%" /><br/>< Workflows 목록 확인 ></p>

<p align="center"><img src="images/aa-o-08.png" width="75%" /><br/>< Install Value Pack 실행 ></p>

<p align="center"><img src="images/aa-o-09.png" width="75%" /><br/>< 설치할 패키지 정보 입력 ></p>
> [!NOTE]
> `Username` 은 `admin` 으로 입력\
> `Admin Project` / `Prime Project` 은 `admin` / `project`으로 입력
  
<p align="center"><img src="images/aa-o-10.png" width="75%" /><br/>< Install Value Pack 실행 결과 확인 ></p>

#### 3. vCenter 정보 등록
`Library` > `Workflows` > `Library` > `vCenter` > `Configuration` > `Add a vCenter Server instance` 을 실행시켜 vCenter 를 등록합니다.

<p align="center"><img src="images/aa-o-11.png" width="75%" /><br/>< Add a vCenter Server instance 실행 ></p>

<p align="center"><img src="images/aa-o-12.png" width="75%" /><br/>< vCenter 속성 정보 입력 ></p>

<p align="center"><img src="images/aa-o-13.png" width="75%" /><br/>< vCenter 접속 정보 입력 ></p>
  
> [!NOTE]
> `Username` 은 `administrator@vsphere.local` 으로 입력
  
<p align="center"><img src="images/aa-o-14.png" width="75%" /><br/>< Add a vCenter Server instance 실행 결과 확인 ></p>

#### 4. Endpoint 설정 암호 변경

<p align="center"><img src="images/aa-o-15.png" width="75%" /><br/>TEXT</p>

<p align="center"><img src="images/aa-o-16.png" width="75%" /><br/>TEXT</p>

<p align="center"><img src="images/aa-o-17.png" width="75%" /><br/>TEXT</p>

<p align="center"><img src="images/aa-o-18.png" width="75%" /><br/>TEXT</p>

<p align="center"><img src="images/aa-o-19.png" width="75%" /><br/>TEXT</p>

<p align="center"><img src="images/aa-o-20.png" width="75%" /><br/>TEXT</p>

#### 5. 카탈로그 아이콘 파일 확인
카탈로그 목록에서 표시될 카탈로그의 아이콘을 위한 이미지 파일을 확인합니다. ([Service Broker 설정 중 카탈로그 컨텐츠 아이콘 수정 부분 참조](/docs/bvp/docs/broker.md))
<p align="center"><img src="images/aa-o-21.png" width="75%" /><br/>< 카탈로그 아이콘 파일 확인 ></p>
