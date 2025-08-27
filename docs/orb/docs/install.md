# 설치방법

## 1. VCF 환경 설정

- [VCF5 환경 설정](vcf5.md)
- VCF9 환경 설정: 준비중...

## 2. 오브리움 설치

> [!NOTE]
> `vCenter` 에서 관리자 계정으로 수행

오브리움 OVA를 이용하여 vSphere 환경에 오브리움 VM을 설치하는 과정입니다.

### 2.1. 사전 요구사항

- CPU: 8코어 이상
- MEM: 32GByte 이상
- Disk: 500GByte 이상
- Network: 2 NIC
  - Primary NIC: 서비스용 인터페이스
  - Secondary NIC: 트랜짓 네트워크 연동용 인터페이스

### 2.2. OVA 배포

다운로드한 최신 오브리움 OVA 파일을 vCenter를 통해 배포합니다.

> [!NOTE]
> 설치 가이드는 vCenter 8.0.3.00500 버전에서 Athena-1a 버전의 배포 화면입니다. 버전에 따라 화면 구성이 다를 수 있습니다.

<p align="center"><img src="images/vc-01.png" width="75%" /><br/>< vCenter 화면 접속 ></p>

<p align="center"><img src="images/vc-02.png" width="75%" /><br/>< 인벤토리에서 OVF 배포 실행 ></p>

<p align="center"><img src="images/vc-03.png" width="75%" /><br/>< 오브리움 OVA 파일 지정 ></p>

<p align="center"><img src="images/vc-04.png" width="75%" /><br/>< VM 이름 및 폴더 결정 ></p>

<p align="center"><img src="images/vc-05.png" width="75%" /><br/>< 자원 위치 결정 ></p>

<p align="center"><img src="images/vc-06.png" width="75%" /><br/>< 자원 디테일 확인 ></p>

<p align="center"><img src="images/vc-07.png" width="75%" /><br/>< 데이터스토어 결정 ></p>

<p align="center"><img src="images/vc-08.png" width="75%" /><br/>< 네트워크 연결 ></p>

오브리움 네트워크는 2가지 네트워크 연결이 필요합니다.

- X-REGION-SEGMENT
  - VCF5 환경: AVN 글로벌 세그먼트에 연결합니다. 일반적으로 VCF5의 AVN 글로벌 네트워크는 VIDM, Aria Automation 및 Aria Operations 가 배포되는 네트워크 입니다.
  - VCF9 환경: 준비중...
- TRANSIT-SEGMENT
  - VCF5 환경: EVCS에서 설정한 트랜짓 세그먼트에 연결합니다. 트랜짓 세그먼트를 통해 VM 콘솔 연결및 VM에 대한 DNS 서비스, 프리셋 서비스를 제공합니다.
  - VCF9 환경: 준비중...

`IP allocation` 은  반드시 `Static - Manual` 로 설정합니다.

<p align="center"><img src="images/vc-09.png" width="75%" /><br/>< 오브리움 네트워크 설정 ></p>

기본적인 네트워크 설정을 합니다. 서비스 네트워크 설정과 트랜짓 네트워크 설정이 있습니다.

- 서비스: 도메인 이름 기반의 오브리움 서비스를 제공하기 위한 필수 요소를 설정합니다.
  - 도메인: 오브리움이 서비스 되는 도메인 영역을 설정합니다.
  - 호스트이름: 도메인 영역 내 오브리움의 호스트 이름을 설정합니다. FQDN이 아닌 단일 호스트이름으로 설정해야 하며, 최종적으로 `https://{호스트이름}.{도메인}` 형식으로 접속 URL이 결정됩니다.
  - 서비스 IP 주소: 서비스를 제공하는 IP 주소 입니다.
  - 서비스 서브넷 프리픽스: 서비스 IP 주소가 동작하는 서브넷 프리픽스 입니다. 최종 서브넷 IP는 `{서비스 IP 주소}/{서비스 서브넷 프리픽스}` 형태가 됩니다.
  - 서비스 게이트웨이: 서비스 네트워크의 게이트웨이 IP 주소 입니다.
  - 서비스 DNS 서버: 도메인내 DNS 쿼리 서비스를 제공하는 DNS 서버 IP 주소 입니다.
- 트랜짓: 오브리움이 클라우드 내부에서 다양한 서비스를 제공하기위한 인터페이스 입니다.
  - 트랜짓 IP 주소: 트랜짓 망에서 오브리움의 IP 주소 입니다.
  - 트랜짓 서브넷 프리픽스: 트랜짓 IP 주소가 동작하는 서브넷 프리픽스 입니다. 최종 서브넷 IP는 `{트랜짓 IP 주소}/{트랜짓 서브넷 프리픽스}` 형태가 됩니다.

<p align="center"><img src="images/vc-10.png" width="75%" /><br/>< 오브리움 접근제어 설정 ></p>

- 시스템 접근 키: BVP의 `Get Package Keys` 워크플로우 실행의 결과로 나온 `accessKey` 항목입니다.
- 시스템 보안 키: BVP의 `Get Package Keys` 워크플로우 실행의 결과로 나온 `secretKey` 항목입니다.
- 오브리움 관리자 계정: 오브리움의 서비스 관리자 계정입니다. 클라우드 서비스가 제공되지는 않으며 VMware SSO 연동 및 서비스 엔드포인트 연결 작업을 수행하는 계정입니다. 계정 시스템(AD/LDAP)과 연결할 경우 계정 시스템이 보유한 계정과 겹치지 않는 ID를 제공해야 합니다.
- 오브리움 관리자 암호: 오브리움 관리자의 암호 입니다.

<p align="center"><img src="images/vc-11.png" width="75%" /><br/>< 오브리움 설정 확인 및 배포 ></p>

<p align="center"><img src="images/vc-13.png" width="75%" /><br/>< 배포 완료 후 전원 켬 ></p>

전원이 켜지고 최초 부팅시점에서, 입력한 값을 토대로 오브리움은 네트워크 및 오브리움 서비스가 자동 설정 됩니다.
최초 부팅시에는 설정에 따른 컨테이너 빌드 과정을 수행하므로 부팅 후 오브리움 서비스가 실행되기까지 시간이 조금 걸릴 수 있습니다.
오브리움에 콘솔에 로그인 후 `docker ps -a` 명령을 통해 컨테이너의 상태를 확인 할 수 있습니다.

<p align="center"><img src="images/check-docker.png" width="75%" /><br/>< 도커 컨테이너 상태 확인 ></p>

`orbrium-nginx` 컨테이너가 `Healthy` 상태로 실행되고 있다면 정상 상태입니다.

> [!TIP]
> 오브리움 OVA의 `root` 계정 암호는 배포시 입력한 `오브리움 관리자 암호` 와 동일합니다.
> 오브리움 OVA의 경우 `root` 암호는 상시 변경 가능하고 서비스에 대한 영향도는 없습니다.


## 3. 오브리움 계정 정보 연동

## 4. 오브리움 프로바이더 & 엔드포인트 연동

> [!NOTE]
> 오브리움에서 오브리움 관리자 계정으로 수행

오브리움에 VMware SSO 환경을 연동하고 클라우드 자원 관리 서비스를 연동하는 작업을 수행합니다.

<p align="center"><img src="images/orb-adm-01.png" width="75%" /><br/>< 오브리움 초기 화면 ></p>

오브리움에 접속합니다. 접속 URL은 `https://{호스트이름}.{도메인}` 입니다. `로그인 페이지로 이동` 버튼을 눌러 로그인창으로 이동합니다.

<p align="center"><img src="images/orb-adm-02.png" width="75%" /><br/>< 오브리움 로그인 창 ></p>

> [!NOTE]
> OVA 배포시 설정한 오브리움 관리자 계정 및 암호를 이용하여 로그인을 합니다.

<p align="center"><img src="images/orb-adm-03.png" width="75%" /><br/>< 관리자 프로바이더 화면 ></p>

<p align="center"><img src="images/orb-adm-04.png" width="75%" /><br/>< 프로바이더 등록 ></p>

VMware SSO 프로바이더를 연동합니다. 플랫폼 유형에 따라 정해진 값을 입력합니다.

- VCF5 유형
  - 이름: 자유롭게 구분 가능한 이름을 사용합니다.
  - 호스트 이름: VIDM의 FQDN을 입력합니다. VIDM 서비스가 외부 노출용 FQDN과 시스템용 FQDN이 분리되어 구성되어 있다면, 외부 노출용 FQDN을 입력합니다.
  - 디렉토리 도메인: VIDM에 설정한 디렉토리 도메인을 입력합니다. VIDM에 디렉토리를 설정하지 않았다면, 입력한 디렉토리 도메인으로 JIT(Just In Time) 디렉토리가 VIDM에 생성됩니다.
  - Access Key: VIDM에서 생성한 오브리움 SSO 클라이언트 ID를 입력합니다.
  - Secret Key: VIDM에서 생성한 오브리움 SSO 클라이언트의 공유 압호를 입력합니다.
- VCF9 유형: 준비중...

<p align="center"><img src="images/orb-adm-05.png" width="75%" /><br/>< 프로바이더 확인 ></p>

정상적으로 등록이 완료되면 상태가 `ON` 으로 표시됩니다.

<p align="center"><img src="images/orb-adm-06.png" width="75%" /><br/>< 관리자 엔드포인트 화면 ></p>

<p align="center"><img src="images/orb-adm-07.png" width="75%" /><br/>< 엔드포인트 등록 ></p>

- VCF5
  - Aria Automation 유형
    - 프로바이더: SSO로 연결된 프로바이더를 선택합니다.
    - 이름: 입력한 이름으로 리전 이름이 결정됩니다. 입력하지 않는다면 Aria Automation의 브랜딩 이름이 자동으로 설정됩니다.
    - 호스트이름: Aria Automation의 FQDN을 입력합니다.
    - 관리자 프로젝트: BVP 설치시 생성한 관리자 프로젝트 이름을 입력합니다. 기본 설정은 `admin` 입니다.
    - 프라임 프로젝트: BVP 설치시 생성한 프라임 프로젝트 이름을 입력합니다. 기본 설정은 `project` 입니다.
    - 사용자 이름: Aria Automation의 Organization Owner 및 모든 서비스의 관리자 권한을 가진 계정을 입력합니다. 일반적으로 `admin` 입니다.
    - 비밀번호: 사용자의 암호를 입력합니다.
- VCF9: 준비중...

<p align="center"><img src="images/orb-adm-08.png" width="75%" /><br/>< 엔드포인트 확인 ></p>

<p align="center"><img src="images/orb-adm-09.png" width="75%" /><br/>< 계정 연동 확인 ></p>

계정 시스템에 등록된 사용자를 검색하여 정상적으로 조회 되는지 확인합니다. 만약 모든 프로젝트에 대한 접근 권한을 주고 싶다면 `+등록하기` 버튼을 눌러 해당 계정을 클라우드 관리자로 등록 할 수 있습니다.

<p align="center"><img src="images/orb-adm-10.png" width="75%" /><br/>< 로그 아웃 ></p>

> [!TIP]
> 오브리움 관리자의 로그아웃은 좌하단 `설정 버튼(Cog)` > `개인 설정` > `로그아웃` 으로 합니다.

## 5. 오브리움 시작
