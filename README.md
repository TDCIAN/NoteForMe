# NoteForMe

## 네트워크 계층 구조 파악

(1) 네트워크 개념
- 네트워크란 원하는 정보를 원하는 수신자 또는 기기에 정확하게 전송하기 위한 기반 인프라이다.
- 거리에 따른 네트워크 분류
  - WAN(광대역 네트워크)
    - LAN에 비해 전송 거리가 넓음. 라우팅 알고리즘이 필요
    - LAN 대비 에러율이 높고 전송 지연이 큼

  - LAN(근거리 네트워크)
    - 한 건물 또는 작은 지역을 커버하는 네트워크


(2) OSI(Open System Interconnection) 7계층
  - 국제 표준화 기구인 ISO(International Standardization Organization)에서 개발
  - 컴퓨터 네트워크 프로토콜 디자인과 통신을 계층으로 나누어 설명한 개방형 시스템 상호 연결 모델
  - 각 계층은 서로 독립적으로 구성되어 있고, 각 계층은 하위 계층의 기능을 이용하여 상위 계층에 기능을 제공한다.
  - 1계층인 물리 계층부터 7계층인 애플리케이션 계층으로 정의되어 있다.
  - 계층을 지날 때마다 헤더(Header)가 붙는데, 이것은 해당 계층의 기능과 관련된 제어 정보가 포함되어있다.
  - 제어 정보들은 모두 운영체제가 제공하는 프로토콜에 의해 송신 측에서는 계층을 지날 때마다 덧붙여서 추가되고, 수신 측에서는 계층을 지날 때마다 제거된다.
  - OSI 7 Layer의 특징
    - 물리(Physical) 계층
      - 설명: 실제 장비들을 연결하기 위한 연결 장치
      - 장비: 허브, 리피터
        - (1) 허브: 여러 대의 컴퓨터를 연결하여 네트워크로 보내거나, 하나의 네트워크로 수신된 정보를 여러 대의 컴퓨터로 송신하기 위한 장비
        - (2) 리피터: 디지털 신호를 증폭시켜 주는 역할을 하여 신호가 약해지지 않고 컴퓨터로 수신되도록 하는 장비


    - 데이터 링크(Data Link) 계층
      - 설명: 오류와 흐름을 제거하여 신뢰성 있는 데이터를 전송
      - 장비: 브리지, 스위치
        - (1) 브리지: 두 개의 근거리통신망(LAN)을 서로 연결해 주는 통신망 연결 장치
        - (2) L2 스위치
          - 느린 전송속도의 브리지, 허브의 단점을 개선하기 위해서, 출발지에서 들어온 프레임을 목적지 MAC 주소 기반으로 빠르게 전송시키는 데이터 링크 계층의 통신 장치
          - L2 스위치는 종류에 따라 3가지 방식 중 하나를 사용
            - Store and Forwarding: 데이터를 전부 받은 후 다음 처리를 하는 방식
            - Cut Through: 데이터의 목적지 주소만 확인 후 바로 전송 처리하는 방식
            - Fragment Free: 프레임의 앞 64바이트만을 읽어 에러를 처리하고 목적지 포트로 전송하는 방식
          - L2, L3, L4 스위치는 OSI 중 어떤 계층에서 수행되는가에 따라 구분
         - (3) NIC
          - Network Interface Card의 약자
          - 외부 네트워크와 접속하여 가장 빠른 속도로 데이터를 주고받을 수 있게 컴퓨터 내에 설치되는 장치
         - (4) 스위칭 허브
          - 스위치 기능을 가진 허브
          - 사용되는 대부분의 허브가 스위칭 허브


    - 네트워크(Network) 계층
      - 설명: 다수의 중개 시스템 중 올바른 경로를 선택하도록 지원
      - 장비: 라우터, 게이트웨이, L3 스위치, 유무선 인터넷 공유기, 망(백본) 스위칭 허브
        - (1) 라우터
          - LAN과 LAN을 연결하거나 LAN과 WAN을 연결하기 위한 인터넷 네트워킹 장비
          - 패킷의 위치를 추출하여, 그 위치에 대한 최적의 경로를 지정하며, 이 경로를 따라 데이터 패킷을 다음 장치로 전송시키는 장비
          - 라우팅 프로토콜은 경로 설정을 하여 원하는 목적지까지 지정된 데이터가 안전하게 전달되도록 함
        - (2) 게이트웨이
          - 프로토콜을 서로 다른 통신망에 접속할 수 있게 해주는 장치
          - LAN에서 다른 네트워크에 데이터를 보내거나 다른 네트워크로부터 데이터를 받아들이는 출입구 역할
        - (3) L3 스위치
          - 3계층에서 네트워크 단위들을 연결하는 통신 장비
          - IP 레이어에서의 스위칭을 수행하여 외부로 전송
          - 라우터와의 경계가 모호
        - (4) 유무선 인터넷 공유기
          - 외부로부터 들어오는 인터넷 라인을 연결하여 유선으로 여러 대의 기계를 연결하거나 무선 신호로 송출하면서 여러 대의 컴퓨터가 하나의 인터넷 라인을 공유할 수 있도록 하는 네트워크 장비
        - (5) 망(백본) 스위칭 허브
          - 광역 네트워크를 커버하는 스위칭 허브
          - 예를 들어 경남권 스위칭, 부산권 스위칭 등 대단위 지역을 커버함


    - 전송(Transport) 계층
      - 설명: 송신, 수신 프로세스 간의 연결
      - 장비: L4 스위치
        - (1) L4 스위치
          - 4계층에서 네트워크 단위들을 연결하는 통신 장비
          - TCP/UDP 등 스위칭 수행
          - FTP, HTTP 등을 구분하여 스위칭하는 로드 밸런싱 가능
          - 애플리케이션 레이어에서 파악이 가능한 이메일 내용 등 정교한 로드 밸런싱 수행 불가
          - 4계층 정보인 TDP/UDP 포트번호를 분석하여 포워딩을 결정하고 QoS와 GLB / SLB 기능을 제공하는 스위치

    - 세션(Session) 계층
      - 설명: 송신, 수신 간의 논리적 연결
      - 장비: 호스트(PC 등)

    - 표현(Presentation) 계층
      - 설명: 코드 문자 등을 번역하여 일관되게 전송하고 압축, 해제, 보안 기능도 담당
      - 장비: 호스트(PC 등)

    - 응용(Application) 계층
      - 설명: 사용자 친화 환경 제공(이메일, 웹 등)
      - 장비: 호스트(PC 등)


### 애플리케이션 공격 기법 유형

- HTTP GET 플러딩(Flooding)
  - HTTP 캐시 옵션을 조작하여 캐싱 서버가 아닌 웹 서버가 직접 처리하도록 유도, 웹 서버 자원을 소진시키는 서비스 거부 공격

- Slowloris(Slow HTTP Header DoS)
  - HTTP GET 메서드를 사용하여 헤더의 최종 끝을 알리는 개행 문자열인 \r\n\r\n(Hex: 0d 0a 0d 0a)을 전송하지 않고, \r\n(Hex: 0d 0a)만 전송하여 대상 웹 서버와 연결 상태를 장시간 지속시키고 연결 자원을 모두 소진시키는 서비스 거부 공격

- RUDY(Slow HTTP POST DoS)
  - 요청 헤더의 Content-Length를 비정상적으로 크게 설정하여 메시지 바디 부문을 매우 소량으로 보내 계속 연결 상태를 유지시키는 공격

- Slow HTTP Read DoS
  - TCP 윈도 크기와 데이터 처리율을 감소시킨 상태에서 (Zero Window Packet) 다수 HTTP 패킷을 지속적으로 전송하여대상 웹 서버의 연결 상태가 장시간 지속. 연결 자원을 소진시키는 서비스 거부 공격

- Hulk DoS
  - 공격자가 공격 대상 웹 사이트 웹 페이지 주소(URL)를 지속적으로 변경하면서 다량으로 GET 요청을 발생시키는 서비스 거부 공격

- Hash DoS
  - 조작된 많은 수의 파라미터를 POST 방식으로 웹 서버로 전달하여 다수의 해시 충돌(Collision)을 발생시켜서 자원을 소모시키는 서비스 거부 공격



### 소프트웨어 테스트 원리

(1) 테스팅은 결함이 존재함을 밝히는 것
- 결함이 존재함을 밝히는 활동
- 결함이 없다는 것을 증명할 수는 없음
- 결함을 줄이는 활동

(2) 완벽한 테스팅은 불가능
- 완벽하게 테스팅하려는 시도는 불필요한 시간과 자원낭비
- 무한 경로(한 프로그램 내의 내부조건은 무수히 많을 수 있음), 무한 입력값(입력이 가질 수 있는 모든 값의 조합이 무수히 많음)으로 인한 테스트 어려움

(3) 개발 초기에 테스팅 시작
- 조기 테스트 설계 시 장점: 테스팅 결과를 단시간에 알 수 있고, 테스팅 기간 단축, 재작업을 줄여 개발 기간 단축 및 결함 예방
- SW 개발 초기 체계적인 분석 및 설계가 수행되지 못하면 그 결과가 프로젝트 후반에 영향을 미치게 되어 비용이 커진다는 요르돈의 법칙(Snowball Effect, 눈덩이 법칙) 적용

(4) 결함집중
- 적은 수의 모듈에서 대다수의 결함이 발견됨
- 소프트웨어 테스트에서 오류의 80%는 전체 모듈의 20% 내에서 발견
- 파레토 법칙(Pareto Principle)의 내용인 80 대 20 법칙 적용

(5) 살충제 패러독스
- 동일한 테스트 케이스에 의한 반복적 테스트는 새로운 버그를 찾지 못함
- 테스트 케이스의 정기적 리뷰와 개선 및 다른 시각에서의 접근이 필요

(6) 테스팅은 정황에 의존적
- 소프트웨어의 성격에 맞게 테스트 실시
- 정황과 비즈니스 도메인에 따라 테스트를 다르게 수행

(7) 오류-부재의 궤변
- 요구사항을 충족시켜주지 못한다면, 결함이 없다고 해도 품질이 높다고 볼 수 없음


### 프로토콜의 3요소
(1) 구문(Syntax)
- 시스템 간의 정보 전송을 위한 데이터 형식, 코딩, 신호 레벨 등의 규정

(2) 의미(Semantic)
- 시스템 간의 정보 전송을 위한 제어 정보로 조정과 에러 처리를 위한 규정

(3) 타이밍(Timing)
- 시스템 간의 정보 전송을 위한 속도 조절과 순서 관리 규정


### 비선점형 스케줄링 알고리즘 유형
(1) 우선순위(Priority)
- 동작방식
  - 프로세스별로 우선순위가 주어지고, 우선순위에 따라 CPU를 할당함
  - 동일 순위는 FCFS(First Come, First Service)
- 특징
  - 주요/긴급 프로세스에 대한 우선 처리
  - 설정, 자원 상황 등에 따른 우선순위 선정

(2) 기한부(Deadline)
- 동작방식
  - 작업들이 명시된 시간이나 기한 내에 완료되도록 계획
- 특징
  - 요청에 명시된 시간 내 처리를 보장

(3) FCFS(First Come First Service)
- 동작 방식
  - 프로세스가 대기 큐에 도착한 순서에 따라 CPU를 할당함
  - FIFO 알고리즘이라고도 함
- 특징
  - 도착한 순서대로 처리

(4) SJF(Shortest Job First)
- 동작 방식
  - 프로세스가 도착하는 시점에 따라 그 당시 가장 작은 서비스 시간을 갖는 프로세스가 종료 시까지 자원 점유
  - 준비 큐 작업 중 가장 짧은 작업부터 수행, 평균 대기시간 최소
  - CPU 요구 시간이 긴 작업과 짧은 작업 간의 불평등이 심하여, CPU 요구 시간이 긴 프로세스는 기아 현상 발생
- 특징
  - 기아 현상 발생 가능성

(5) HRN(Highest Response Ration Next)
- 동작 방식
  - 대기 중인 프로세스 중 현재 응답률(Response Ratio)이 가장 높은 것을 선택
  - SJF의 약점인 기아 현상을 보완한 기법으로 긴 작업과 짧은 작업 간의 불평등 완화
  - HRN의 우선순위 = (대기 시간 + 서비스 시간) / 서비스 시간
- 특징
  - 기아 현상(starvation) 최소화 기법


### 결합도와 응집도

* 결합도
(1) 내용 결합도(Content Coupling)
- 다른 모듈 내부에 있는 변수나 기능을 다른 모듈에서 사용하는 경우의 결합도

(2) 공통 결합도(Common Coupling)
- 파라미터가 아닌 모듈 밖에 선언되어 있는 전역 변수를 참조하고 전역 변수를 갱신하는 식으로 상호작용하는 경우의 결합도

(3) 외부 결합도(External Coupling)
- 두 개의 모듈이 외부에서 도입된 데이터 포맷, 통신 프로토콜, 또는 디바이스 인터페이스를 공유할 경우의 결합도

(4) 제어 결합도(Control Coupling)
- 단순 처리할 대상인 값만 전달되는 게 아니라 어떻게 처리를 해야 한다는 제어 요소가 전달되는 경우의 결합도

(5) 스탬프 결합도(Stamp Coupling)
- 모듈 간의 인터페이스로 배열이나 객체, 구조 등이 전달되는 경우의 결합도

(6) 자료 결합도(Data Coupling)
- 모듈 간의 인터페이스로 전달되는 파라미터를 통해서만 모듈 간의 상호작용이 일어나는 경우의 결합도



* 응집도
(1) 우연적 응집도(Coincidental Cohesion)
- 모듈 내부의 각 구성요소가 연관이 없을 경우의 응집도

(2) 논리적 응집도(Logical Cohesion)
- 유사한 성격을 갖거나 특정 형태로 분류되는 처리 요소들이 한 모듈에서 처리되는 경우의 응집도

(3) 시간적 응집도(Temporal Cohesion)
- 연관된 기능이라기보다는 특정 시간에 처리되어야 하는 활동들을 한 모듈에서 처리할 경우의 응집도

(4) 절차적 응집도(Procedural Cohesion)
- 모듈이 다수의 관련 기능을 가질 때 모듈 안의 구성요소들이 그 기능을 순차적으로 수행할 경우의 응집도

(5) 통신적 응집도(Communication Cohesion)
- 동일한 입력과 출력을 사용하여 다른 기능을 수행하는 활동들이 모여 있을 경우의 응집도

(6) 순차적 응집도(Sequential Cohesion)
- 모듈 내에서 한 활동으로부터 나온 출력값을 다른 활동이 사용할 경우의 응집도

(7) 기능적 응집도(Functional Cohesion)
- 모듈 내부의 모든 기능이 단일한 목적을 위해 수행되는 경우의 응집도


### 데이터 모델 구성요소
(1) 연산(Operation)
- 데이터베이스에 저장된 실제 데이터를 처리하는 작업에 대한 명세
- 릴레이션을 조작하기 위한 관계 연산을 나타내며 관계 연산에는 select, project, join, division 등이 있음

(2) 구조(Structure)
- 논리적으로 표현된 개체 타입 간의 관계
- 데이터 구조 및 정적 성질을 표현
- 릴레이션에 해당하는 것으로 데이터를 원잣값으로 갖는 이차원의 테이블로 표현

(3) 제약조건(Constraint)
- 데이터베이스에 저장될 수 있는 실제 데이터의 논리적인 제약 조건


### IPC(Inter-Process Communication)
- IPC는 프로세스 간 통신 기술이다
- IPC 기법의 종류
(1) 메시지 큐
- 메시지(또는 패킷) 단위로 동작하여 프로세스 간 통신함

(2) 공유메모리
- 한 프로세스의 일부분을 다른 프로세스와 공유

(3) 소켓
- 클라이언트와 서버 프로세스 둘 사이에 통신을 가능하게 함

(4) 세마포어
- 프로세스 사이의 동기를 맞추는 기능을 제공함


### DoS 공격

(1) DoS(Denial of Service) 공격의 개념
- 시스템을 악의적으로 공격해 해당 시스템의 자원을 부족하게 하여 원래 의도된 용도로 사용하지 못하게 하는 공격이다.
- 특정 서버에 수많은 접속 시도를 만들어 다른 이용자가 정상적으로 서비스 이용을 하지 못하게 하거나, 서버의 TCP 연결을 소진시키는 등의 공격이다.

(2) DoS 공격의 종류
- 지역 시스템 공격
  - 실제 대상 시스템에 접근하여 서버 하드웨어에 직접 과부하를 주는 공격
  - 예: 메모리 고갈, 프로세스 서비스 거부, 디스크 서비스 거부 등
- 원격 네트워크 공격
  - 공격자가 목표시스템에 접근하지 않고 원격지에서 인터넷 등을 이용한 공격
  - 서비스를 제공받지 못하거나 실제 시스템에 영향

(3) DDoS 공격 구성요소
- 핸들러(Handler)
  - 마스터 시스템의 역할을 수행하는 프로그램
- 에이전트(Agent)
  - 공격 대상에게 직접 공격을 가하는 시스템
- 마스터(Master)
  - 공격자에게서 직접 명령을 받는 시스템
  - 여러 대의 에이전트를 관리하는 역할
- 공격자(Attacker)
  - 공격을 주도하는 해커의 컴퓨터
- 데몬(Daemon) 프로그램
  - 에이전트 시스템의 역할을 수행하는 프로그램


### 자원 고갈 공격
- 서버 간 핸드셰이크를 통해 통신이 연결되는 정상 트래픽과 달리 DoS 공격은 정상 접속을 시도하는 오픈된 소켓에 트래픽을 집중시킨다.
- 공격이 임계치에 도달하면 사용자들은 네트워크에 전혀 접속할 수 없게 된다.

- SYN 플러딩 (SYN Flooding)
  - TCP 프로토콜의 구조적인 문제를 이용한 공격
  - 서버의 동시 가용 사용자 수를 SYN 패킷만 보내 점유하여 다른 사용자가 서버를 사용 불가능하게 하는 공격
  - 공격자는 ACK를 발송하지 않고 계속 새로운 연결 요청을 하게 되어 서버는 자원할당을 해지하지 않고 자원만 소비하여 자원이 고갈
- UDP 플러딩 (UDP Flooding)
  - 대량의 UDP 패킷을 만들어 임의의 포트 번호로 전송하여 응답 메시지(ICMP Destination Unreachable)를 생성하게 하여 지속해서 자원을 고갈시키는 공격
  - ICMP 패킷은 변조되어 공격자에게 전달되지 않아 대기함

- 스머프(Smurf)
  - 출발지 주소를 공격 대상의 IP로 설정하여 네트워크 전체에게 ICMP Echo 패킷을 직접 브로드캐스팅(Directed Broadcasting)하여 마비시키는 공격
  - 바운스(Bounce) 사이트라고 불리는 제3의 사이트를 이용해 공격

- PoD(Ping of Death)
  - 큰 사이즈의 패킷을 의도적으로 목표시스템으로 발생시켜 시스템이서비스할 수 없는 상태로 만드는 공격

### 애플리케이션 공격
- HTTP GET 플러딩(Flooding)
  - Cache Control Attack 공격
  - Http 캐시 옵션을 조작하여 캐싱 서버가 아닌 웹서버가 직접 처리하도록 유도, 웹서버 자원을 소진시키는 서비스 거부 공격

- Slowloris(Slow HTTP Header DoS)
  - HTTP GET 메소드를 사용하여 헤더의 최종 끝을 알리는 개행 문자열인 ＼r＼n＼r＼n(Hex: 0d 0a 0d 0a)을 전송하지 않고, ＼r＼n(Hex: 0d 0a)만 전송하여 대상 웹서버와 연결상태를 장시간 지속시키고 연결 자원을 모두 소진시키는 서비스 거부 공격

- RUDY(Slow HTTP POST DoS)
  - 요청 헤더의 Content-length를 비정상적으로 크게 설정하여 메시지 바디 부분을 매우 소량으로 보내 계속 연결 상태를 유지시키는 공격
  - 예: Content-Length: 9999999 설정 이후 1바이트씩 전송하여 연결 유지

- Slow HTTP Read DoS
  - TCP 윈도 크기와 데이터 처리율을 감소시킨 상태에서(Zero Window Packet) 다수 HTTP 패킷을 지속적으로 전송하여 대상 웹 서버의 연결 상태가 장시간 지속, 연결 자원을 소진시키는 서비스 거부 공격

- Hulk DoS
  - 공격자가 공격 대상 웹사이트 웹 페이지 주소(RUL)를 지속적으로 변경하면서 다량으로 GET 요청을 발생시키는 서비스 거부 공격

- Hash DoS
  - 조작된 많은 수의 파라미터를 POST 방식으로 웹 서버로 전달하여 다수의 해시 충돌(Collision)을 발생시켜서 자원을 소모시키는 서비스 거부 공격


### 소프트웨어 개발방법론의 종류
(1) 구조적 방법론(Structured Development)
- 전체 시스템을 기능에 따라 나누어 개발하고, 이를 통합하는 분할과 정복 접근 방식의 방법론
- 프로세스 중심의 하향식 방법론
- 구조적 프로그래밍 표현을 위해 나씨-슈나이더만(Nassi-Shneiderman) 차트 사용
  - 나씨-슈나이더만 차트 특징
    - 논리의 기술에 중점을 둔 도형식 표현 방법
    - 연속, 선택 및 다중 선택, 반복 등의 제어 논리 구조로 표현
    - 조건이 복합되어 있는 곳의 처리를 시각적으로 명확히 식별하는 데 적합

(2) 정보공학 방법론(Information Engineering Development)
- 정보 시스템 개발에 필요한 관리 절차와 작업 기법을 체계화한 방법론
- 개발주기를 이용해 대형 프로젝트를 수행하는 체계적인 방법론

(3) 객체지향 방법론(Object-Oriented Development)
- '객체'라는 기본 단위로 시스템을 분석 및 설계하는 방법론
- 복잡한 현실 세계를 사람이 이해하는 방식으로 시스템에 적용하는 방법론
- 객체, 클래스, 메시지를 사용

(4) 컴포넌트 기반 방법론(CBD; Component Based Development)
- 소프트웨어를 구성하는 컴포넌트를 조립해서 하나의 새로운 응용 프로그램을 작성하는 방법론
- 개발 기간 단축으로 인한 생산성 향상
- 새로운 기능 추가 쉬움(확장성)
- 소프트웨어 재사용이 가능

(5) 애자일 방법론(Agile Development)
- 절차보다는 사람이 중심이 되어 변화에 유연하고 신속하게 적응하면서 효율적으로 시스템을 개발할 수 있는 신속 적응적 경량 개발방법론
- 애자일은 개발 과정의 어려움을 극복하기 위해 적극적으로 모색한 방법론

(6) 제품 계열 방법론(Product Line Development)
- 특정 제품에 적용하고 싶은 공통된 기능을 정의하여 개발하는 방법론
- 임베디드 소프트웨어를 작성하는 데 유용한 방법론
- 영역 공학과 응용 공학으로 구분
  - 영역 공학: 영역 분석, 영역 설계, 핵심 자산을 구현하는 영역
  - 응용 공학: 제품 요구분석, 제품 설계, 제품을 구현하는 영역


### 공통 모듈 테스트의 종류
(1) 화이트박스 테스트
- 응용 프로그램의 내부 구조와 동작을 검사하는 소프트웨어 테스트 방식으로 소스 코드를 보면서 테스트 케이스를 다양하게 만들어 테스트를 수행
- 화이트박스 테스트 유형
  - 구문 커버리지 = 문장(Statement) 커버리지
    - 프로그램 내의 모든 명령문을 적어도 한 번 수행하는 커버리지
    - 조건문 결과와 관계없이 구문 실행 개수로 계산

  - 결정 커버리지 = 선택(Decision) 커버리지 = 분기(Branch) 커버리지
    - (각 분기의) 결정 포인트 내의 전체 조건식이 적어도 한 번은 참(T)과 거짓(F)의 결과를 수행하는 커버리지
    - 구문 커버리지를 포함

  - 조건(Condition) 커버리지
    - (각 분기의) 결정 포인트 내의 개별 조건식이 적어도 한 번은 참과 거짓의 결과가 되도록 수행하는 테스트 커버리지
    - 구문 커버리지를 포함

  - 조건/결정(Condition/Decision) 커버리지
    - 전체 조건식뿐만 아니라 개별 조건식도 참 한 번, 거짓 한 번 결과가 되도록 수행하는 테스트 커버리지

  - 변경 조건/결정(Modified Condition/Decision) 커버리지
    - 개별 조건식이 다른 개별 조건식에 영향을 받지 않고 전체 조건식에 독립적으로 영향을 주도록 함으로써 조건/결정 커버리지를 향상시킨 커버리지

  - 다중 조건(Multiple Condition) 커버리지
    - 결정 조건 내 모든 개별 조건식의 모든 가능한 조합을 100% 보장하는 커버리지

  - 기본 경로(Base Path) 커버리지 = 경로 커버리지
    - 수행 가능한 모든 경로를 테스트하는 기법

  - 제어 흐름 테스트(Control Flow Testing)
    - 프로그램 제어 구조를 그래프 형태로 나타내어 내부 로직을 테스트하는 기법

  - 데이터 흐름 테스트(Data Flow Testing)
    - 제어 흐름 그래프에 데이터 사용현황을 추가한 그래프를 통해 테스트하는 기법

(2) 메서드 기반 테스트
- 공통 모듈의 외부에 공개된 메서드 기반의 테스트
- 메서드에 서로 다른 파라미터 값을 호출하면서 다양한 테스트를 수행

(3) 화면 기반 테스트
- 사용자용 화면이 있는 경우, 각각의 화면단위로 단위모듈을 개발 후에 화면에 직접 데이터를 입력하여 테스트를 수행
- 화면기반 테스트는 화면과 연계된 서비스, 비즈니스 컴포넌트 및 공통 컴포넌트를 한꺼번에 단위 테스트에 참여

(4) 테스트 드라이버 / 테스트 스텁
- 테스트 드라이버: 하위 모듈은 있지만, 상위 모듈은 없는 경우 사용하는 기법
- 테스트 스텁: 상위 모듈은 있지만, 하위 모듈은 없는 경우 사용하는 기법



### 데이터베이스 정규화 단계

(1) 1정규형(1NF): 원자값으로 구성

(2) 2정규형(2NF): 부분 함수 종속 제거(완전 함수적 종속 관계)

(3) 3정규형(3NF): 이행함수 종속 제거

(4) 보이스-코드 정규형(BCNF): 결정자 후보키가 아닌 함수 종속 제거

(5) 4정규형(4NF): 다치(다중 값) 종속 제거

(6) 5정규형(5NF): 조인 종속 제거


### 입력 데이터 검증 및 표현에 대한 취약점 종류
(1) XSS(Cross Site Script)
- 검증되지 않은 외부 입력 데이터가 포함된 웹 페이지가 전송되는 경우, 사용자가 해당 웹 페이지를 열람함으로써 웹 페이지에 포함된 부적절한 스크립트가 실행되는 공격

(2) 사이트 간 요청 위조(CSRF)
- 사용자가 자신의 의지와는 무관하게 공격자가 의도한 행위를 특정 웹 사이트에 요청하게 하는 공격

(3) SQL 삽입(Injection)
- 응용 프로그램의 보안 취약점을 이용해서 악의적인 SQL 구문을 삽입, 실행시켜서 데이터베이스(DB)의 접근을 통해 정보를 탈취 하거나 조작 등의 행위를 하는 공격 기법



### 생성 패턴
(1) Builder
- 복잡한 인스턴스를 조립하여 만드는 구조로, 복합 객체를 생성할 때 객체를 생성하는 방법(과정)과 객체를 구현(표현)하는 방법을 분리함으로써 동일한 생성 절차에서 서로 다른 표현 결과를 만들 수 있는 디자인 패턴
- 생성과 표기를 분리해서 복잡한 객체를 생성


(2) Prototype
- 처음부터 일반적인 원형을 만들어 놓고, 그것을 복사한 후 필요한 부분만 수정하여 사용하는 패턴으로, 생성할 객체의 원형을 제공하는 인스턴스에서 생성할 객체들의 타입이 결정되도록 설정하며 객체를 생성할 때 갖춰야 할 기본 형태가 있을 때 사용되는 디자인 패턴
- 기존 객체를 복제함으로써 객체를 생성

(3) Factory Method
- 상위 클래스에서 객체를 생성하는 인터페이스를 정의하고, 하위 클래스에서 인스턴스를 생성하도록 하는 방식으로, 상위 클래스에서는 인스턴스를 만드는 방법만 결정하고, 하위 클래스에서 그 데이터의 생성을 책임지고 조작하는 함수들을 오버라이딩 하여 인터페이스와 실제 객체를 생성하는 클래스를 분리할 수 있는 특성을 갖는 디자인 패턴
- 생성할 객체의 클래스를 국한하지 않고 객체를 생성

(4) Abstract Factory
- 구체적인 클래스에 의존하지 않고 서로 연관되거나 의존적인 객체들의 조합을 만드는 인터페이스를 제공하는 패턴으로 이 패턴을 통해 생성된 클래스에서는 사용자에게 인터페이스(API)를 제공하고, 구체적인 구현은 Concrete Product 클래스에서 이루어지는 특징을 갖는 디자인 패턴
- 동일한 주제의 다른 팩토리를 묶음

(5) Singleton
- 전역 변수를 사용하지 않고 객체를 하나만 생성하도록 하며, 생성된 객체를 어디에서든지 참조할 수 있도록 하는 디자인 패턴
- 한 클래스에 한 객체만 존재하도록 제한



### 구조 패턴
(1) Bridge
- 기능의 클래스 게층과 구현의 클래스 계층을 연결하고, 구현부에서 추상 계층을 분리하여 추상화된 부분과 실제 구현 부분을 독립적으로 확장할 수 있는 디자인 패턴
- 구현뿐만 아니라 추상화된 부분까지 변경해야 하는 경우 활용

(2) Decorator
- 기존에 구현되어 있는 클래스에 필요한 기능을 추가해 나가는 설계 패턴으로 기능 확장이 필요할 때 객체 간의 결합을 통해 기능을 동적으로 유연하게 확장할 수 있게 해주어 상속의 대안으로 사용하는 디자인 패턴
- 기존 객체의 결합을 통해 기능을 동적으로 유연하게 확장

(3) Facade
- 복잡한 시스템에 대하여 단순한 인터페이스를 제공함으로써 사용자와 시스템 간 또는 여타 시스템과의 결합도를 낮추어 시스템 구조에 대한 파악을 쉽게 하는 패턴으로 오류에 대해서 단위별로 확인할 수 있게 하며, 사용자의 측면에서 단순한 인터페이스 제공을 통해 접근성을 높일 수 있는 디자인 패턴
- 통합된 인터페이스 제공

(4) Flyweight
- 다수의 객체로 생성될 경우 모두가 갖는 본질적인 요소를 클래스화하여 공유함으로써 메모리를 절약하고, '클래스의 경량화'를 목적으로 하는 디자인 패턴
- 여러 개의 '가상 인스턴스'를 제공하여 메모리 절감

(5) Proxy
- '실체 객체에 대한 대리 객체'로 실제 객체에 대한 접근 이전에 필요한 행동을 취할 수 있게 만들며, 이 점을 이용해서 미리 할당하지 않아도 상관없는 것들을 실제 이용할 때 할당하게 하여 메모리 용량을 아낄 수 있으며, 실체 객체를 드러나지 않게 하여 정보은닉의 역할도 수행하는 디자인 패턴
- 특정 객체로의 접근을 제어하기 위한 용도로 사용

(6) Composite
- 객체들의 관계를 트리 구조로 구성하여 부분-전체 계층을 표현하는 패턴으로, 사용자가 단일 객체와 복합 객체 모두 동일하게 다루도록 하는 패턴
- 복합 객체와 단일 객체를 동일하게 취급

(7) Adapter
- 기존에 생성된 클래스를 재사용할 수 있도록 중간에서 맞춰주는 역할을 하는 인터페이스를 만드는 패턴으로, 상속을 이용하는 클래스 패턴과 위임을 이용하는 인스턴스 패턴의 두 가지 형태로 사용되는 디자인 패턴
- 인터페이스가 호환되지 않는 클래스들을 함께 이용할 수 있도록 타 클래스의 인터페이스를 기존 인터페이스에 덧씌움

