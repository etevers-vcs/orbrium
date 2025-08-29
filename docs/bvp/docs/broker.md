# Service Broker 설정
VMware Aria Automation Service Broker는 카탈로그 항목을 요청하고 관리할 수 있는 단일 지점을 제공합니다.\
클라우드 관리자는 사용자가 클라우드 벤더 지역이나 데이터스토어에 배포할 수 있는 릴리스된 VMware Aria Automation Assembler 클라우드 템플릿을 가져와서 카탈로그 항목을 생성합니다.\
사용자는 프로비저닝 프로세스를 요청하고 모니터링할 수 있습니다. 배포 후에는 배포된 카탈로그 항목을 배포 수명 주기 동안 관리합니다.

<p align="center"><img src="images/aa-sb-01.png" width="75%" /><br/>< Service Broker 선택 ></p>

Automation Service Broker에서는 카탈로그의 컨텐츠를 나타내는 아이콘을 사용자 지정하고, 가져온 템플릿에 대한 요청 양식을 사용자 지정할 수 있습니다. \
요청 양식을 사용자 지정할 때 카탈로그 항목을 요청하는 사용자가 값을 제공할 수 있도록 입력 매개 변수를 디자인할 수도 있습니다. 사용자 지정 옵션이 양식에 표시되는 방법을 사용자 지정할 수 있습니다.

<p align="center"><img src="images/aa-sb-02.png" width="75%" /><br/>< Content & Policies > Content > Virtual Machine 의 Customize form 선택 ></p>

> [!IMPORTANT]
> Virtual Machine 에서 사용할 OS 이미지의 Root Password 값을 지정한다.

<p align="center"><img src="images/aa-sb-03.png" width="75%" /><br/>< form 내용 중 _ㅡmetadata_hidden 탭 필드 중 Root Password 선택 후 필드 속성 중 Value 값 수정 ></p>

> [!IMPORTANT]
> `Admin Username` 은 `orbadmin`을 디폴트값으로 지정한다.\
> `Admin Password` 는 `Admin Username` 으로 로그인시 사용할 임의의 값을 지정한다.

<p align="center"><img src="images/aa-sb-04.png" width="75%" /><br/>< form 내용 중 _ㅡmetadata_hidden 탭 필드 중 Admin Password 선택 후 필드 속성 중 Value 값 수정 ></p>

<p align="center"><img src="images/aa-sb-05.png" width="75%" /><br/>< Broadcom Value Pack 제공 전체 카탈로그 목록 ></p>

## 카탈로그 컨텐츠 아이콘 수정
Automation Service Broker에서 카탈로그의 컨텐츠를 나타내는 아이콘을 사용자 지정하고, 카탈로그 항목에 대해 배포된 인스턴스 수를 제한하고, 가져온 템플릿에 대한 요청 양식을 사용자 지정할 수 있습니다. \
요청 양식을 사용자 지정할 때 카탈로그 항목을 요청하는 사용자가 값을 제공할 수 있도록 입력 매개 변수를 디자인할 수도 있습니다. 사용자 지정 옵션이 양식에 표시되는 방법을 사용자 지정할 수 있습니다.\

`Orchestrator` > `Assets` > `Resources` > `BVP` > `Files` 아래의 Orbrium Icon 파일을 Export 하여 다운로드하고 파일의 압축을 푼다.

<p align="center"><img src="images/aa-sb-24.png" width="75%" /><br/>< Orbrium Icon 파일 선택 ></p>

<p align="center"><img src="images/aa-sb-25.png" width="75%" /><br/>< OrbriumIcons.zip 파일 Export 실행 ></p>

카탈로그들의 아이콘 수정을 위한 작업으로 각 카탈로그 선택 후 `Configure Item` 메뉴를 선택한 후 수정 화면에서 `CHANGE ICON` 을 선택하여 다운로드한 아이콘 중 선택한 카탈로그와 같은 이름의 아이콘을 선택 후 저장한다.

<p align="center"><img src="images/aa-sb-06.png" width="75%" /><br/>< 카탈로그 선택 후 Configure Item 선택 ></p>

<p align="center"><img src="images/aa-sb-07.png" width="75%" /><br/>< Configure Item 수정 ></p>

<p align="center"><img src="images/aa-sb-08.png" width="75%" /><br/>< 모든 카탈로그 아이콘 설정 완료 ></p>

##  카탈로그 항목 배포 예
Broadcom Value Pack 에서 제공하는 카탈로그 항목들의 배포 예는 아래와 같습니다.

### 1. 카탈로그: Project 배포

<p align="center"><img src="images/aa-sb-09.png" width="75%" /><br/>< 카탈로그: Project ></p>

<p align="center"><img src="images/aa-sb-10.png" width="75%" /><br/>< Basic Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-11.png" width="75%" /><br/>< User Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-26.png" width="75%" /><br/>< Approval Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-27.png" width="75%" /><br/>< Zone Restrictions 입력 예 ></p>

<p align="center"><img src="images/aa-sb-12.png" width="75%" /><br/>< 카탈로그 배포 확인 ></p>

신규 프로젝트로 배포된 카탈로그의 목록을 확인합니다.

<p align="center"><img src="images/aa-sb-13.png" width="75%" /><br/>< 신규 프로젝트가 사용 가능한 카탈로그 목록 ></p>

### 2. 카탈로그: Virtual Private Cloud 배포

<p align="center"><img src="images/aa-sb-14.png" width="75%" /><br/>< Basic Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-15.png" width="75%" /><br/>< Policy Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-16.png" width="75%" /><br/>< 카탈로그 배포 확인 ></p>

### 3. 카탈로그: Segment 배포

<p align="center"><img src="images/aa-sb-17.png" width="75%" /><br/>< Basic Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-18.png" width="75%" /><br/>< Network Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-19.png" width="75%" /><br/>< 카탈로그 배포 확인 ></p>

### 4. 카탈로그: Virtual Machine 배포

<p align="center"><img src="images/aa-sb-20.png" width="75%" /><br/>< Basic Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-21.png" width="75%" /><br/>< Computing Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-22.png" width="75%" /><br/>< Network Settings 입력 예 ></p>

<p align="center"><img src="images/aa-sb-23.png" width="75%" /><br/>< Storage Settings 입력 예 ></p>
