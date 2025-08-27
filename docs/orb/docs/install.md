# 설치방법

## 1. 고유 키 확인

> [!NOTE]
> `admin` 계정으로 수행

<p align="center"><img src="images/aa-key-01.png" width="75%" /><br/>< Orchestrator 서비스 모듈 선택 ></p>

<p align="center"><img src="images/aa-key-02.png" width="75%" /><br/>< Get Package Keys 워크플로우 실행 ></p>

`Get Package Keys` 워크플로우를 실행 (`RUN`) 합니다. 실행 결과는 다음과 같이 나타납니다.

<p align="center"><img src="images/aa-key-03.png" width="75%" /><br/>< 워크플로우 결과 화면 ></p>

워크플로우가 정상으로 수행되었다면 `Completed` 상태가 되며, 실행 결과 하단의 `Variables` 탭으로 이동하면 `accessKey` 와 `secretKey` 를 확인 할 수 있습니다.
이 키는 오브리움 한 사이트(=회사, =Org) 단위로 고유한 값이어야 하며, 만약 오브리움에 여러 Aria Automation(=Multi Region)을 연결해야 한다면, 각 Aria Automation의 `accessKey` 와 `secretKey` 를 동일하게 수정해 주어야 합니다.
`accessKey` 와 `secretKey` 는 오브리움 배포 전 언제든지 `Orchestrator` > `Configuration` > `BVP` > `Endpoint` > `Orbrium` > `data` 항목에서 수정 가능합니다.

확인한 `accessKey` 와 `secretKey` 를 오브리움 설치를 위해 임시로 복사해 놓습니다.\ `accessKey`와 `secretKey`는 영속적으로 유지되어야 하며 변경 불가능 하기 때문에, 반드시 보안을 지켜 사용해야 합니다.


