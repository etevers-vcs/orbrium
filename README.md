# 오브리움 (Orbrium)

<p align="center"><strong>오브리움 메인페이지에 오신것을 환영합니다</strong></p>
<p align="center"><img src="/docs/img/orbrium-logo.png?raw=true" width="50%"></p>
<p align="center"><img src="/docs/img/orbrium-home.png?raw=true" width="75%"></p>

## 영업 자료

**<p align="center"><a href="https://github.com/etevers-vcs/orbrium/raw/refs/heads/main/files/pptx/VCF-VUE-Orbrium-Brochure.pdf">VCF VUE(Orbrium) 브로셔 (.pdf)</a></p>**

**<p align="center"><a href="https://github.com/etevers-vcs/orbrium/raw/refs/heads/main/files/pptx/Etevers-VMware-Orbrium-Athena-1a-Salesdeck.pptx">세일즈 자료 (.pptx)</a></p>**

**<p align="center"><a href="https://github.com/etevers-vcs/orbrium/raw/refs/heads/main/files/pptx/Etevers-VMware-Orbrium-Athena-1a-Techdeck.pptx">기술 자료 (.pptx)</a></p>**

## 매뉴얼

**<p align="center"><a href="docs/evcs">EVCS: Etevers VMware Cloud Standards</a> > <a href="https://play.google.com/books/reader?id=PAFhEQAAQBAJ&pg=GBS.PP1&hl=ko">e-Book 링크</a></p>**

**<p align="center"><a href="docs/bvp">BVP: Broadcom Value Pack</a> > <a href="https://github.com/etevers-vcs/orbrium/raw/refs/heads/main/files/broadcom-value-pack/com.bvp.package">바이너리 패키지 다운로드</a></p>**

**<p align="center"><a href="docs/orb">ORB: Orbrium</a> > <a href="https://youngwoocokr-my.sharepoint.com/:u:/g/personal/hc_jang_etevers_com/ESHEWlbY8JFDpX6PNl5SkYABGWen0Je0NcG0TZZcnSXUag?e=ujP368">OVA 이미지 다운로드</a></p>**

## 오브리움 릴리스 노트

### Brontes

- VCF5 & VCF9 지원
- Roadmap
  - 2025-09: 사전 기술 검증
  - 2025-10: 프로젝트 개시
  - 2025-12: GA

### Athena

> [!NOTE]
> Latest Stable: 1A

#### 1B

- Front-End
  - 과금 최적화
  - UX 흐름 최적화
- Back-End
  - User 정보 관리 최적화
  - SingleTon 스케줄 작업 최적화

#### 1A > [다운로드](https://youngwoocokr-my.sharepoint.com/:u:/g/personal/hc_jang_etevers_com/ESHEWlbY8JFDpX6PNl5SkYABGWen0Je0NcG0TZZcnSXUag?e=ujP368)

- Front-End
  - 클라우드 관리자 페이지
- Back-End
  - VCF9 지원을 확장을 위한 추상화
  - Pygma Playform v2 적용
  - 향상된 안정성
- Installer
  - OVA 기반 자동배포

### Arthemis

> [!WARNING]
> DEPRECATED

#### 1D

- Front-End
  - 변경사항 없음
- Back-End
  - 변경사항 없음
- Installer
  - 폐쇄망에서 이미지 빌드 작업 오류 혜결
  - "truststore" 로 오인표기 되어있던 부분을 "truststores" 로 정상표기
  - truststores 디렉토리 사전생성

#### 1C

- Front-End
  - Home Network Design 일부 기능 개선
  - 가상머신 상세페이지 메트릭 보기 버그 픽스
- Back-End
  - common 라이브러리 버전 변경
  - wsa_directory_domain 설정 추가: WSA에서 기 설정된 LDAP/AD에 대한 연결 정보 제공
- Installer
  - "1.upgrade.sh" 업그레이드 자동화 스크립트 추가

#### 1B

- 1A 설치과정 버그 픽스
  - Broadcom Value Pack에서 AccessKey 발급시 소문자 + 숫자조합만 가능하도록 변경
