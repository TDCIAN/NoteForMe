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


### 행위 패턴
(1) Mediator
- 객체지향 설계에서 객체의 수가 너무 많아지면 서로 간 통신을 위해 복잡해져서 객체지향에서 가장 중요한 느슨한 결합의 특성을 해칠 수 있기 때문에 이를 해결하는 방법으로 중간에 이를 통제하고 지시할 수 있는 역할을 하는 중재자를 두고, 중재자에게 모든 것을 요구하여 통신의 빈도수를 줄여 객체지향의 목표를 달성하게 해주는 디자인 패턴
- 상호작용의 유연한 변경을 지원

(2) Interpreter
- 언어의 다양한 해석, 구체적으로 구문을 나누고 그 분리된 구문의 해석을 맡는 클래스를 각각 작성하여 여러 형태의 언어 구문을 해석할 수 있게 만드는 디자인 패턴
- 문법 자체를 캡슐화하여 사용

(3) Iterator
- 컬렉션 구현 방법을 노출시키지 않으면서도 그 집합체 안에 들어있는 모든 항목에 접근할 방법을 제공하는 디자인 패턴
- 내부구조를 노출하지 않고, 복잡 객체의 원소를 순차적으로 접근 가능하게 해주는 행위 패턴

(4) Template Method
- 어떤 작업을 처리하는 일부분을 서브 클래스로 캡슐화해 전체 일을 수행하는 구조는 바꾸지 않으면서 특정 단계에서 수행하는 내역을 바꾸는 패턴으로 일반적으로 상위 클래스(추상 클래스)에는 추상 메서드를 통해 기능의 골격을 제공하고, 하위 클래스(구체 클래스)의 메서드에서는 세부처리를 구체화하는 방식으로 사용하며 코드 양을 줄이고 유지보수를 용이하게 만드는 특징을 갖는 디자인 패턴
- 상위 작업의 구조를 바꾸지 않으면서 서브 클래스로 작업의 일부분을 수행

(5) Observer
- 한 객체의 상태가 바뀌면 그 객체에 의존하는 다른 객체들에 연락이 가고 자동으로 내용이 갱신되는 방법으로 일대 다의 의존성을 가지며 상호작용하는 객체 사이에서는 가능하면 느슨하게 결합하는 디자인 패턴
- 객체의 상태 변화에 따라 다른 객체의 상태도 연동, 일대다 의존

(6) State
- 객체 상태를 캡슐화하여 클래스화함으로써 그것을 참조하게 하는 방식으로 상태에 따라 다르게 처리할 수 있도록 행위 내용을 변경하여, 변경 시 원시 코드의 수정을 최소화할 수 있고, 유지보수의 편의성도 갖는 디자인 패턴
- 객체의 상태에 따라 행위 내용을 변경

(7) Visitor
- 각 클래스의 데이터 구조로부터 처리 기능을 분리하여 별도의 클래스를 만들어 놓고 해당 클래스의 메서드가 각 클래스를 돌아다니며 특정 작업을 수행하도록 만드는 패턴으로, 객체의 구조는 변경하지 않으면서 기능만 따로 추가하거나 확장할 때 사용하는 디자인 패턴
- 특정 구조를 이루는 복합 객체의 원소 특성에 따라 동작을 수행할 수 있도록 지원하는 행위

(8) Command
- 실행될 기능을 캡슐화함으로써 주어진 여러 기능을 실행할 수 있는 재사용성이 높은 클래스를 설계하는 패턴으로 하나의 추상 클래스에 메서드를 만들어 각 명령이 들어오면 그에 맞는 서브클래스가 선택되어 실행 되는특징을 갖는 디자인 패턴 
- 요구사항을 객체로 캡슐화

(9) Strategy
- 알고리즘 군을 정의하고(추상 클래스) 같은 알고리즘을 각각 하나의 클래스로 캡슐화한 다음, 필요할 때 서로 교환해서 사용할 수 있게 하는 패턴, 행위를 클래스로 캡슐화해 동적으로 행위를 자유롭게 바꿀 수 있게 해주는 패턴
- 행위 객체를 클래스로 캡슐화해 동적으로 행위를 자유롭게 변환

(10) Memento
- 클래스 설계 관점에서 객체의 정보를 저장할 필요가 있을 때 적용하는 디자인 패턴으로 Undo 기능을 개발할 때 사용하는 디자인 패턴
- 객체를 이전 상태로 복구시켜야 하는 경우, '작업취소(Undo)' 요청 가능

(11) Chain of Responsibility
- 정적으로 어떤 기능에 대한 처리의 연결이 하드 코딩되어 있을 때 기능 처리의 연결 변경이 불가능한데, 이를 동적으로 연결된 경우에 따라 다르게 처리될 수 있도록 연결한 디자인 패턴
- 한 요청을 2개 이상의 객체에서 처리


### 대칭키 암호 방식 종류
(1) DES(Data Encryption Standard)
- 1975년 미국의 연방 표준국(NIST)에서 발표한 대칭 키 기반의 블록 암호화 알고리즘
- 블록 크기는 64bit, 키 길이는 56bit인 페이스텔(Feistel) 구조
- DES를 3번 적용하여 보안을 더욱 강화한 3DES도 활용됨

(2) AES(Advanced Encryption Standard)
- 2001년 미국 표준 기술 연구소(NIST)에서 발표한 블록 암호화 알고리즘
- DES의 개인 키에 대한 전사적 공격이 가능해지고, 3DES의 성능문제를 극복하기 위해 개발
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 192bit, 256bit로 분류
- AES의 라운드 수는 10, 12, 14라운드로 분류되며, 한 라운드는 SubBytes, ShiftRows, MixColumns, AddRoundKey의 4가지 계층으로 구성

(3) SEED
- 1999년 한국인터넷진흥원(KISA)이 개발한 블록 암호화 알고리즘
- 128bit 비밀키로부터 생성된 16개의 64bit 라운드 키를 사용하여 총 16회의 라운드를 거쳐 128bit의 평문 블록을 128bit 암호문 블록으로 암호화하여 출력하는 방식
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 256bit로 분류

(4) ARIA(Academy, Research Institute, Agency)
- 2004년 국가정보원과 산학연구협회가 개발한 블록 암호화 알고리즘
- ARIA는 학계(Academy), 연구기관(Research Institue), 정부(Agency)의 영문 앞글자로 구성
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 192bit, 256bit로 분류
- ARIA는 경량 환경 및 하드웨어의 효율성 향상을 위해 개발되었으며, ARIA가 사용하는 대부분의 연산은 XOR과 같은 단순한 바이트 단위 연산으로 구성

(5) IDEA(International Data Encryption)
- DES를 대체하기 위해 스위스 연방기술 기관에서 개발한 블록 암호화 알고리즘
- 128bit의 키를 사용하여 64bit의 평문을 8라운드에 거쳐 64bit의 암호문을 만듦

(6) LFSR(Linear Feedback Shift Register)
- 선형 되먹임 시프트 레지스터는 시프트 레지스터의 일종으로, 레지스터에 입력되는 값이 이전 상태 값들의 선형 함수로 계산되는 구조로 되어 있는 스트림 암호화 알고리즘
- 이때 사용되는 선형 함수는 주로 배타적 논리합(XOR)이고, LFSR의 초기 비트 값은 시드(Seed)라고 함


### 비대칭키(공개키) 암호 방식 종류
(1) 디피-헬만(Diffie-Hellman)
- 최초의 공개키 알고리즘으로 W.Diffie와 M.Hellman이 1976년에 고안한 알고리즘으로써 유한 필드 내에서 이산대수의 계산이 어려운 문제를 기본 원리로 하고 있음
- 공개키 암호 방식의 개념을 이용하여 두 사용자 간에 공통의 암호화 키를 안전하게 공유할 방법을 제시하였으며, 많은 키 분배 방식에 관한 연구의 기본이 됨(최초의 비밀키 교환 프로토콜)

(2) RSA(Rivest-Shamir-Adleman)
- 1977년 3명의 MIT 수학 교수(Rivest, Shamir, Adleman)가 고안한 큰 인수의 곱을 소인수분해하는 수학적 알고리즘을 이용하는 공개키 암호화 알고리즘
- 비밀키의 복호화가 어려운 RSA 안정성은 소인수분해 문제의 어려움에 근거를 두고 있음

(3) ECC(Elliptic Curve Cryptography)
- 1985년 코블리치와 밀러가 RSA 암호 방식에 대한 대안으로 처음 제안
- 타원 곡선 암호(ECC)는 유한체 위에서 정의된 타원곡선 군에서의 이산대수의 문제에 기초한 공개키 암호화 알고리즘
- PKI 기반의 RSA의 문제점인 속도와 안정성을 해결하기 위해 타원 기반 구조체의 안정성과 효율성을 기반으로 생성되었고, RSA보다 키의 비트 수를 적게 하면서 동일한 성능을 제공하는 것이 가장 큰 특징

(4) ElGamel
- T.ElGamel이 1984년에 제안한 공개키 알고리즘
- 이산대수의 계산이 어려운 문제를 기본 원리로 하고 있으며, RSA와 유사하게 전자서명과 데이터 암복호화에 함께 사용 가능


### 해시 암호 방식 종류
(1) MD5(Message-Digest Algorithm 5)
- 1991년 로널드 라이베스트가 MD4를 개선한 암호화 알고리즘으로, 프로그램이나 파일의 무결성 검사에 사용
- 각각의 512bit짜리 입력 메시지 블록에 대해 차례로 동작하여 128bit의 해시값을 생성하는 해시 알고리즘

(2) SHA-1(Secure Hash Algorithm)
- 1993년 NSA에서 미 정부 표준으로 지정되었고, DSA(Digital Signature Algorithm)에서 사용
- 160bit의 해시값을 생성하는 해시 알고리즘

(3) SHA-256/384/512
- SHA 알고리즘의 한 종류로서 256bit의 해시값을 생성하는 해시함수
- AES(Advanced Encryption Standard, 미 연방 표준 알고리즘)의 키 길이긴 128, 192, 256bit에 대응하도록 출력 길이를 늘인 해시 알고리즘

(4) HAS-160
- 국내 표준 서명 알고리즘 KCDSA(Korean Certificate-based Digital Signature Algorithm)를 위하여 개발된 해시 함수
- MD5와 SHA1의 


### 객체지향 설계원칙(SOLID)
(1) SRP(Single Responsibility Principle, 단일 책임 원칙)
- 객체는 단 하나의 책임만을 가져야 함
- 어떤 클래스를 변경해야 하는 이유는 오직 하나뿐이어야 하며(책임 = 변경 사유), 같은 이유로 변화하는 것끼리 묶고, 다른 이유로 변화하는 것끼리는 분리함

(2) OCP(Open-Closed Principle, 개방 폐쇄 원칙)
- 기존의 코드를 변경하지 않으면서 기능을 추가할 수 있도록 설계가 되어야 함
- 소프트웨어 개체(Classes, Modules, Functions 등)는 확장에는 열려 있고 수정 시에는 닫혀 있어야 함

(3) LSP(Likov Substitution Principle, 리스코프 치환 원칙)
- 일반화 관계(is a kind of 관계)에 대한 것으로 자식 클래스는 최소한 자신의 부모 클래스에서 가능한 행위는 수행할 수 있어야 함
- 하위 클래스 및 타입들은 상위 타입들이 사용되는 곳에 대체될 수 있어야 하는 설계 원칙
- 자식 클래스가 부모 클래스 기능을 재정의 하지 않으면 대체 가능함

(4) ISP(Interface, Segregation Princple, 인터페이스 분리의 원칙)
- 인터페이스를 클라이언트에 특화되도록 분리하라는 설계 원칙
- 하나의 일반적인 인터페이스보다 구체적인 여러 개의 인터페이스가 나음

(5) DIP(Dependency Inversion Principle, 의존성 역전의 원칙)
- 의존 관계를 맺을 때 변화하기 쉬운 것 또는 자주 변화하는 것보다는 변화하기 어렵거나 거의 변화가 없는 것에 의존하라는 것임
- 추상화된(인터페이스 등) 것에 의존하게 만들고 구체 클래스에 의존하도록 만들지 않도록 함



### 테스트 목적에 따른 분류
(1) 회복 테스트(Recovery Testing)
- 시스템에 고의로 실패를 유도하고, 시스템의 정상적 복귀 여부를 테스트하는 기법

(2) 안전 테스트(Security Testing)
- 불법적인 소프트웨어가 접근하여 시스템을 파괴하지 못하도록 소스 코드 내의 보안적인 결함을 미리 점검하는 테스트 기법

(3) 성능 테스트(Performance Testing)
- 사용자의 이벤트에 시스템이 응답하는 시간, 특정 시간 내에 처리하는 업무량, 사용자 요구에 시스템이 반응하는 속도 등을 측정하는 테스트 기법

(4) 구조 테스트(Structure Testing)
- 시스템의 내부 논리 경로, 소스 코드의 복잡도를 평가하는 테스트 기법

(5) 회귀 테스트(Regression Testing)
- 회귀 테스트는 오류를 제거하거나 수정한 시스템에서 오류 제거와 수정에 의해 새로이 유입된 오류가 없는지 확인하는 일종의 반복 테스트 기법

(6) 병행 테스트(Parallel Testing)
- 변경된 시스템과 기존 시스템에 동일한 데이터를 입력 후 결과를 비교하는 테스트 기법


### 절차형 SQL 종류
(1) 프로시저(Procedure)
- 일련의 쿼리들을 마치 하나의 함수처럼 실행하기 위한 쿼리의 집합

(2) 사용자 정의함수(User-Defined Function)
- 일련의 SQL 처리를 수행하고, 수행 결과를 단일 값으로 반환할 수 있는 절차형 SQL

(3) 트리거(Trigger)
- 데이터베이스 시스템에서 삽입, 갱신, 삭제 등의 이벤트가 발생할 때마다 관련 작업이 자동으로 수행되는 절차형 SQL


### 통신 프로토콜
(1) NetBIOS(Network Basic Input/Output System)
- 응용계층(7계층)의 애플리케이션 프로그램에 API를 제공하여 상호 통신할 수 있도록 해주는 프로토콜

(2) ICMP(Internet Control Message Protocol)
- 네트워크 계층(3계층)에서 IP 패킷을 처리할 때 발생되는 문제를 알려주고, 수신지 도달 불가 메시지를 사용하여 수신지 또는 서비스에 도달할 수 없는 


### 소프트웨어 아키텍처 4+1 뷰
(1) 유스케이스 뷰(Usecase View)
- 유스케이스 또는 아키텍처를 도출하고 설계하며 다른 뷰를 검증하는 데 사용되는 뷰
- 사용자, 설계자, 개발자, 테스트 관점

(2) 논리 뷰(Logical View)
- 시스템의 기능적인 요구사항이 어떻게 제공되는지 설명해주는 뷰
- 설계자, 개발자 관점

(3) 프로세스 뷰(Process View)
- 시스템의 비기능적인 속성으로서 자원의 효율적인 사용, 병행 실행, 비동기, 이벤트 처리 등을 표현한 뷰
- 개발자, 시스템 통합자 관점

(4) 구현 뷰(Implementation View)
- 개발 환경 안에서 정적인 소프트웨어 모듈의 구성을 보여주는 뷰
- 컴포넌트 구조와 의존성을 보여주고 컴포넌트에 관한 부가적인 정보 정의

(5) 배포 뷰(Deployment View)
- 컴포넌트가 물리적인 아키텍처에 어떻게 배치되는가를 매핑해서 보여주는 뷰


### 프로세스와 스레드
(1) 프로세스: 프로세스는 CPU에 의해 처리되는 사용자 프로그램, 시스템 프로그램. 즉 실행 중인 프로그램
(2) 스레드: 프로세스보다 가벼운, 독립적으로 수행되는 순차적인 제어의 흐름이며, 실행 단위임

### 럼바우의 객체지향 분석 절차
(1) 객체 모델링: 시스템의 정적 구조 표현
(2) 동적 모델링: 객체의 제어 흐름 / 상호 반응 표현
(3) 기능 모델링: 데이터값의 변화 과정 표현



### 애플리케이션 공격
(1) HTTP GET 플러딩(Flooding)
- Cache Control Attack 공격
- Http 캐시 옵션을 조작하여 캐싱 서버가 아닌 웹서버가 직접 처리하도록 유도, 웹서버 자원을 소진시키는 서비스 거부 공격

(2) Slowloris(Slow HTTP Header DoS)
- HTTP GET 메소드를 사용하여 헤더의 최종 끝을 알리는 개행 문자열인 \r\n\r\n(Hex: 0d 0a 0d 0a)을 전송하지 않고, \r\n(Hex: 0d 0a)만 전송하여 대상 웹서버와 연결상태를 장시간 지속시키고 연결 자원을 모두 소진시키는 서비스 거부 공격

(3) RUDY(Slow HTTP POST DoS)
- 요청 헤더의 Content-length를 비정상적으로 크게 설정하여 메시지 바디 부분을 매우 소량으로 보내 계속 연결 상태를 유지시키는 공격
- 예: Content-Length: 9999999 설정 이후 1바이트씩 전송하여 연결 유지

(4) Slow HTTP Read DoS
- TCP 윈도 크기와 데이터 처리율을 감소시킨 상태에서(Zero Window Packet) 다수 HTTP 패킷을 지속적으로 전송하여 대상 웹서버의 연결 상태가 장시간 지속, 연결 자원을 소진시키는 서비스 거부 공격

(5) Hulk DoS
- 공격자가 공격 대상 웹사이트 웹 페이지 주소(URL)를 지속적으로 변경하면서 다량으로 GET 요청을 발생시키는 서비스 거부 공격

(6) Hash DoS
- 조작된 많은 수의 파라미터를 POST 방식으로 웹 서버로 전달하여 다수의 해시 충돌(Collision)을 발생시켜서 자원을 소모시키는 서비스 거부 공격



### 공통 모듈 테스트의 종류

(1) 화이트박스 테스트
- 응용 프로그램의 내부 구조와 동작을 검사하는 소프트웨어 테스트 방식으로 소스 코드를 보면서 테스트 케이스를 다양하게 만들어 테스트를 수행

(2) 메서드 기반 테스트
- 공통 모듈의 외부에 공개된 메서드 기반의 테스트
- 메서드에 서로 다른 파라미터 값을 호출하면서 다양한 테스트를 수행

(3) 화면 기반 테스트
- 사용자용 화면이 있는 경우, 각각의 화면단위로 단위모듈을 개발 후에 화면에 직접 데이터를 입력하여 테스트를 수행
- 화면기반 테스트는 화면과 연계된 서비스, 비즈니스 컴포넌트 및 공통 컴포넌트를 한꺼번에 단위 테스트에 참여

(4) 테스트 드라이버/테스트 스텁
- 기능을 테스트할 수 있는 화면 또는 하위 모듈이 구현되어 있지 않은 경우 테스트 드라이버, 테스트 스텁을 통해 테스트를 수행
- 테스트 드라이버: 하위 모듈은 있지만, 상위 모듈은 없는 경우 사용하는 기법
- 테스트 스텁: 상위 모듈은 있지만, 하위 모듈은 없는 경우 사용하는 기법



### 취약점 공격

(1) 랜드 어택
- 출발지(Source) IP와 목적지(Destination) IP를 같은 패킷 주소로 만들어 보냄으로써 수신자가 자기 자신에게 응답을 보내게 하여 시스템의 가용성을 침해하는 공격기법

(2) 봉크 / 보잉크
- 프로토콜의 오류 제어를 이용한 공격기법으로서 시스템의 패킷 재전송과 재조립이 과부하를 유발
- 봉크: 같은 시퀀스 번호를 계속 보냄
- 보잉크: 일정한 간격으로 시퀀스 번호에 빈 공간 생성

(3) 티어 드롭
- IP 패킷의 재조합 과정에서 잘못된 Fragment Offset 정보로 인해 수신 시스템이 문제를 발생하도록 만드는 DoS 공격
- 공격자는 IP Fragment Offset 값을 서로 중첩되도록 조작하여 전송하고, 이를 수신한 시스템이 재조합하는 과정에서 오류가 발생, 시스템의 기능을 마비시키는 공격 방식




### UI 시 문서의 작성 요건
(1) 완전성(Complete)
- UI 시나리오는 누락이 없어야 하고, 최대한 빠짐없이 가능한 한 상세하게 기술
- 시스템 기능보다 사용자의 태스크에 초점을 맞춰 기술

(2) 일관성(Consistent)
- 서비스에 대한 목표,시스템 및 사용자의 요구사항이 일관성이 있어야 하고, 모든 문서의 UI 스타일(Flow 또는 Layout)을 일관적으로 구성

(3) 이해성(Understandable)
- 처음 접하는 사람도 이해하기 쉽도록 구성하고 설명해야 하고, 이해하지 못하는 추상적인 표현이나 이해하기 어려운 용어는 사용하지 않아야 함

(4) 가독성(Readable)
- 문서를 쉽게 읽을 수 있어야 하고(문서 템플릿과 타이포그래피), 표준화된 탬플릿을 작성하여 적용
- 버전의 넘버링은 v1.0, v2.0 등과 같이 일관성 있게 하고, 시각적인 효과를 위한 하이라이팅은 일관성 있게 활용

(5) 추적 용이성(Traceable)
- 쉽게 추적이 가능해야 하고, 변경 사항들이 언제, 어디서, 어떤 부분들이, 왜 발생하였는지 추적이 쉬워야 함

(6) 수정 용이성(Modifiable)
- 쉽게 변경이 가능해야 하고, 수정 또는 개선 사항을 시나리오에 반영하는 데 있어 쉽게 적용할 수 있어야 함
- 동일한 수정 사항을 위해 여러 문서를 편집하지 않도록 함



### 내외부 송수신 시스템 연계 기술 중 직접 연계 기술
(1) DB 링크(DB Link)
- 데이터베이스에서 제공하는 DB 링크 객체를 이용
- 수신 시스템에서 DB 링크를 생성하고 송신 시스템에서 해당 DB 링크를 직접 참조하는 방식
- 예시: 테이블명@DBLink명

(2) DB 연결(DB Connection)
- 수신 시스템의 WAS에서 송신 시스템 DB로 연결하는 DB 커넥션 풀(DB Connection Pool)을 생성하고 연계 프로그램에서 해당 DB 커넥션 풀 명을 이용하여 연결
- 예시: 송신 시스템의 Data Source = DB Connection Pool 이름

(3) API/Open API
- 송신 시스템의 DB에서 데이터를 읽어서 제공하는 애플리케이션 프로그래밍 인터페이스 프로그램
- API명, 입출력 파라미터 정보가 필요함

(4) JDBC
- 수신 시스템의 프로그램에서 JDBC 드라이버를 이용하여 송신 시스템 DB와 연결
- DBMS 유형, DBMS 서버 IP와 Port, DB 인스턴스(Instance) 정보가 필요

(5) 하이퍼링크(Hyper Link)
- 현재 페이지에서 다른 부분으로 가거나 전혀 다른 페이지로 이동하게 해 주는 속성
- 예시: <a href="url"> Link 대상 </a>



### 테스트 오라클 유형
(1) 참(True) 오라클
- 모든 입력값에 대하여 기대하는 결과를 생성함으로써 발생된 오류를 모두 검출할 수 있는 오라클

(2) 샘플링(Sampling) 오라클
- 특정한 몇 개의 입력값에 대해서만 기대하는 결과를 제공해주는 오라클

(3) 휴리스틱(Heuristic) 오라클
- 샘플링 오라클을 개선한 오라클로, 특정 입력값에 대해 올바른 결과를 제공하고, 나머지 값들에 대해서는 휴리스틱(추정)으로 처리하는 오라클

(4) 일관성 검사(Consistent) 오라클
- 애플리케이션 변경이 있을 때, 수정 전과 후의 결과값이 동일한지 확인하는 오라클



### 자원 고갈 공격
- 서버 간 핸드셰이크를 통해 통신이 연결되는 정상 트래픽과 달리 DoS 공격은 정상 접속을 시도하는 오픈된 소켓에 트래픽을 집중시킨다.
- 공격이 임계치에 도달하면 사용자들은 네트워크에 전혀 접속할 수 없게 된다.

(1) SYN 플러딩(SYN Flooding)
- TCP 프로토콜의 구조적인 문제를 이용한 공격
- 서버의 동시 가용 사용자 수를 SYN 패킷만 보내 점유하여 다른 사용자가 서버를 사용 불가능하게 하는 공격
- 공격자는 ACK를 발송하지 않고 계속 새로운 연결 요청을 하게 되어 서버는 자원할당을 해지하지 않고 자원만 소비하여 자원이 고갈

(2) UDP 플러딩(UDP Flooding)
- 대량의 UDP 패킷을 만들어 임의의 포트 번호로 전송하여 응답 메시지(ICMP Destination Unreachable)를 생성하게 하여 지속해서 자원을 고갈시키는 공격
- ICMP 패킷은 변조되어 공격자에게 전달되지 않아 대기함

(3) 스머프(Smurf)
- 출발지 주소를 공격 대상의 IP로 설정하여 네트워크 전체에게 ICMP Echo 패킷을 직접 브로드캐스팅(Directed Broadcasting)하여 마비시키는 공격
- 바운스(Bounce) 사이트라고 불리는 제3의 사이트를 이용해 공격

(4) PoD(Ping of Death)
- 큰 사이즈의 패킷을 의도적으로 목표시스템으로 발생시켜 시스템이 서비스할 수 없는 상태로 만드는 공격



### 취약점 공격

(1) 랜드 어택(Land Attack)
- 출발지(Source) IP와 목적지(Destination) IP를 같은 패킷 주소로 만들어 보냄으로써 수신자가 자기 자신에게 응답을 보내게 하여 시스템의 가용성을 침해하는 공격기법

(2) 봉크 / 보잉크(Bonk / Boink)
- 프로토콜의 오류 제어를 이용한 공격기법으로서 시스템의 패킷 재전송과 재조립이 과부하를 유발
- 봉크: 같은 시퀀스 번호를 계속 보냄
- 보잉크: 일정한 간격으로 시퀀스 번호에 빈 공간 생성

(3) 티어 드롭(Tear Drop)
- IP 패킷의 재조합 과정에서 잘못된 Fragment Offset 정보로 인해 수신 시스템이 문제를 발생하도록 만드는 DoS 공격
- 공격자는 IP Fragment Offset 값을 서로 중첩되도록 조작하여 전송하고, 이를 수신한 시스템이 재조합하는 과정에서 오류가 발생, 시스템의 기능을 마비시키는 공격 방식



### 고가용성 유형
(1) Hot Standby(상시 대기 방식)
- 가동시스템과 백업시스템으로 구성되어서, 평상시에는 대기 상태를 유지하다가 장애시 전환하는 방식

(2) Mutual Take-Over(상호 인수)
- 2개 시스템이 각각의 고유한 가동 업무 서비스를 수행하다가 한 서버에서 장애가 발생하면 상대 시스템의 자원을 페일 오버하여 동시에 2개의 업무를 수행하는 방식

(3) Concurrent Access(동시적 접근)
- 여러 개의 시스템이 동시에 업무를 나누어 병렬처리하는 방식으로 HA에 참여하는 시스템 전체가 액티브한 상태로 업무를 수행하여 시스템 장애 시에도 다른 시스템으로 페일 오버(Fail Over)하지 않고 가용성을 보장하는 방식



### 단위모듈 4가지 핵심원리

(1) 정보은닉(Information Hiding)
- 어렵거나 변경 가능성이 있는 모듈을 타 모듈로부터 은폐

(2) 분할과 정복(Divide & Conquer)
- 복잡한 문제를 분해, 모듈 단위로 문제 해결

(3) 데이터 추상화(Data Abstraction)
- 각 모듈 자료 구조를 액세스하고 수정하는 함수 내에 자료구조의 표현 내역을 은폐

(4) 모듈 독립성(Module Independency)
- 낮은 결합도와 높은 응집도를 가짐



### DBMS 특징(무일회보효)
(1) 데이터 무결성
- 부적절한 자료가 입력되어 동일한 내용에 대하여 서로 다른 데이터가 저장되는 것을 허용하지 않는 성질

(2) 데이터 일관성
- 삽입, 삭제, 갱신, 생성 후에도 저장된 데이터가 변함없이 일정

(3) 데이터 회복성
- 장애가 발생하였을 시 특정 상태로 복구되어야 하는 성질

(4) 데이터 보안성
- 불법적인 노출, 변경, 손실로부터 보호되어야 하는 성질

(5) 데이터 효율성
- 응답 시간, 저장 공간 활용 등이 최적화되어 사용자, 소프트웨어, 시스템 등의 요구 조건을 만족시켜야 하는 성질



### 테스트 목적에 따른 분류
(1) 회복 테스트(Recovery Testing)
- 시스템에 고의로 실패를 유도하고, 시스템의 정상적 복귀 여부를 테스트하는 기법

(2) 안전 테스트(Security Testing)
- 불법적인 소프트웨어가 접근하여 시스템을 파괴하지 못하도록 소스 코드 내의 보안적인 결함을 미리 점검하는 테스트 기법

(3) 성능 테스트(Performance Testing)
- 사용자의 이벤트에 시스템이 응답하는 시간, 특정 시간 내에 처리하는 업무량, 사용자 요구에 시스템이 반응하는 속도 등을 측정하는 테스트 기법

(4) 구조 테스트(Structure Testing)
- 시스템의 내부 논리 경로, 소스 코드의 복잡도를 평가하는 테스트 기법

(5) 회귀 테스트(Regression Testing)
- 회귀 테스트는 오류를 제거하거나 수정한 시스템에서 오류 제거와 수정에 의해 새로이 유입된 오류가 없는지 확인하는 일종의 반복 테스트 기법

(6) 병행 테스트(Parallel Testing)
- 변경된 시스템과 기존 시스템에 동일한 데이터를 입력 후 결과를 비교하는 테스트 기법



### 대칭키 암호 방식 종류
(1) DES(Data Encryption Standard)
- 1975년 미국의 연방 표준국(NIST)에서 발표한 대칭 키 기반의 블록 암호화 알고리즘
- 블록 크기는 64bit, 키 길이는 56bit인 페이스텔(Feistel) 구조
- DES를 3번 적용하여 보안을 더욱 강화한 3DES도 활용됨

(2) AES(Advanced Encryption Standard)
- 2001년 미국 표준 기술 연구소(NIST)에서 발표한 블록 암호화 알고리즘
- DES의 개인 키에 대한 전사적 공격이 가능해지고, 3DES의 성능 문제를 극복하기 위해 개발
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 192bit, 256bit로 분류
- AES의 라운드 수는 10, 12, 14라운드로 분류되며, 한 라운드는 SubBytes, ShiftRows, MixColumns, AddRoundKey의 4가지 계층으로 구성

(3) SEED
- 1999년 한국인터넷진흥원(KISA)이 개발한 블록 암호화 알고리즘
- 128bit 비밀키로부터 생성된 16개의 64bit 라운드 키를 사용하여 총 16회의 라운드를 거쳐 128bit의 평문 블록을 128bit 암호문 블록으로 암호화하여 출력하는 방식
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 256bit로 분류

(4) ARIA(Academy, Research, Institute, Agency)
- 2004년 국가정보원과 산학연구협회가 개발한 블록 암호화 알고리즘
- ARIA는 학계(Academy), 연구기관(Research Institute), 정부(Agency)의 영문 앞글자로 구성
- 블록 크기는 128bit이며, 키 길이에 따라 128bit, 192bit, 256bit로 분류
- ARIA는 경량 환경 및 하드웨어에서의 효율성 향상을 위해 개발되었으며, ARIA가 사용하는 대부분의 연산은 XOR과 같은 단순한 바이트 연산으로 구성

(5) IDEA(International Data Encryption Algorithm)
- DES를 대체하기 위해 스위스 연방기술 기관에서 개발한 블록 암호화 알고리즘
- 128bit의 키를 사용하여 64bit의 평문을 8라운드에 걸쳐 64bit의 암호문을 만듦

(6) LFSR(Linear Feedback Shift Register)
- 선형 되먹임 시프트 레지스터는 시프트 레지스터의 일종으로, 레지스터에 입력되는 값이 이전 상태 값들의 선형 함수로 계산되는 구조로 되어 있는 스트림 암호화 알고리즘
- 이때 사용되는 선형 함수는 주로 배타적 논리합(XOR)이고, LFSR의 초기 비트 값은 시드(Seed)라고 함


### 비대칭키(공개키) 암호 방식 종류
(1) 디피-헬만(Diffie-Hellman)
- 최초의 공개키 알고리즘으로 W.Diffie와 M.Hellman이 1976년에 고안한 알고리즘으로써 유한 필드 내에서 이산대수의 계산이 어려운 문제를 기본 원리로 하고 있음
- 공개키 암호 방식의 개념을 이용하여 두 사용자 간에 공통의 암호화 키를 안전하게 공유할 방법을 제시하였으며, 많은 키 분배 방식에 관한 연구의 기본이 됨(최초의 비밀키 교환 프로토콜)

(2) RSA(Rivest-Shamir-Adleman)
- 1977년 3명의 MIT 수학 교수(Rivest, Shamir, Adleman)가 고안한 큰 인수의 곱을 소인수분해하는 수학적 알고리즘을 이용하는 공개키 암호화 알고리즘
- 비밀키의 복호화가 어려운 RSA 안정성은 소인수분해 문제의 어려움에 근거를 두고 있음

(3) ECC(Elliptic Curve Cryptography)
- 1985년 코블리치와 밀러가 RSA 암호 방식에 대한 대안으로 처음 제안
- 타원 곡선 암호(ECC)는 유한체 위에서 정의된 타원곡선 군에서의 이산대수의 문제에 기초한 공개키 암호화 알고리즘
- PKI 기반의 RSA의 문제점인 속도와 안정성을 해결하기 위해 타원 기반 구조체의 안정성과 효율성을 기반으로 생성되었고, RSA보다 키의 비트 수를 적게 하면서 동일한 성능을 제공하는 것이 가장 큰 특징

(4) ElGamal
- T.ElGamal이 1984년에 제안한 공개키 알고리즘
- 이산대수의 계산이 어려운 문제를 기본 원리로 하고 있으며, RSA와 유사하게 전자서명과 데이터 암복호화에 함께 사용 가능


### 해시 암호 방식 종류
(1) MD5(Message-Digest algorithm 5)
- 1991년 로널드 라이베스트가 MD4를 개선한 암호화 알고리즘으로, 프로그램이나 파일의 무결성 검사에 사용
- 각각의 512bit짜리 입력 메시지 블록에 대해 차례로 동작하여 128bit의 해시값을 생성하는 해시 알고리즘

(2) SHA-1(Secure Hash Algorithm)
- 1993년 NSA에서 미 정부 표준으로 지정되었고, DSA(Digital Signature Algorithm)에 사용
- 160 bit의 해시값을 생성하는 해시 알고리즘

(3) SHA-256/384/512(Secure Hash Algorithm)
- SHA 알고리즘의 한 종류로서 256bit의 해시값을 생성하는 해시함수
- AES(Advanced Encryption Standard, 미 연방 표준 알고리즘)의 키 길이인 128, 192, 256bit에 대응하도록 출력 길이를 늘인 해시 알고리즘

(4) HAS-160
- 국내 표준 서명 알고리즘 KCDSA(Korean Certificate-based Digital Signature Algorithm)를 위하여 개발된 해시 함수
- MD5와 SHA1의 장점을 취하여 개발된 해시 알고리즘




### 화이트박스 테스트 유형
(1) 구문 커버리지 = 문장 커버리지(Statement Coverage)
(2) 결정 커버리지 = 선택 커버리지 = 분기 커버리지
(3) 조건 커버리지
(4) 조건/결정 커버리지
(5) 변경 조건/결정 커버리지
(6) 다중 조건 커버리지
(7) 기본 경로 커버리지 = 경로 커버리지
(8) 제어 흐름 테스트
(9) 데이터 흐름 테스트


### 비선점형 스케줄링 알고리즘 유형
(1) 우선순위(Priority)
- 프로세스별로 우선순위가 주어지고, 우선순위에 따라 CPU를 할당함
- 동일 순위는 FCFS
- 주요/긴급 프로세스에 대한 우선 처리
- 설정, 자원 상황 등에 따른 우선순위 선정

(2) 기한부(Deadline)
- 작업들이 명시된 시간이나 기한 내에 완료되도록 계획
- 요청에 명시된 시간 내 처리를 보장

(3) FCFS(First Come First Service)
- 프로세스가 대기 큐에 도착한 순서에 따라 CPU를 할당함
- FIFO 알고리즘이라고도 함
- 도착한 순서대로 처리

(4) SJF(Shortest Job First)
- 프로세스가 도착하는 시점에 따라 그 당시 가장 작은 서비스 시간을 갖는 프로세스가 종료 시까지 자원 점유
- 준비 큐 작업 중 가장 짧은 작업부터 수행, 평균 대기 시간 최소
- CPU 요구 시간이 긴 작업과 짧은 작업 간의 불평등이 심하여, CPU 요구 시간이 긴 프로세스는 기아 현상 발생

(5) HRN(Highest Response Ratio Next)
- 대기 중인 프로세스 중 현재 응답률(Response Ratio)이 가장 높은 것을 선택
- SJF의 약점인 기아 현상을 보완한 기법으로 긴 작업과 짧은 작업 간의 불평등 완화
- HRN의 우선순위 = (대기시간 + 서비스 시간) / 서비스 시간
- 기아 현상(starvation) 최소화 기법



### 서버 하드웨어 개발환경
(1) 웹 서버
- HTTP를 이용한 요청/응답을 처리
- 웹 상의 정적 콘텐츠(CSS, Javascript, Image)를 처리
- WEB-WAS-DB의 3계층 구조를 실무에서 활용 - 주요 제품으로 Apache 웹 서버, IIS 웹 서버, Google Web SErver, Nginx 등 존재

(2) 웹 애플리케이션 서버
- 사용자 요청 스레드를 처리하고, 데이터베이스에 접속하여 SQL 쿼리 문에 대한 결과값을 반환
- 주요 제품으로 Tomcat, Weblogic, Jeus, Resin 등 존재

(3) 데이터베이스 서버
- 데이터의 수집, 저장을 위한 용도로 사용
- 연계되는 주요 DBMS로 MySQL, Oracle, MS-SQL, DB2 등 존재

(4) 파일 서버
- 파일 저장 하드웨어로 물리 저장장치를 활용한 서버
- 대용량 HDD, SSD 등의 장치가 존재



### 버퍼 오버플로우 공격유형
(1) 스택 버퍼 오버플로우 공격
- 메모리 영역 중 Local Value나 함수의 Return Address가 저장되는 스택 영역에서 발생하는 오버플로우 공격
- 스택 영역에 할당된 버퍼 크기를 초과하는 양의 데이터(실행 가능 코드)를 입력하여 복귀 주소를 변경하고 공격자가 원하는 임의의 코드를 실행하는 공격 기법

(2) 힙 버퍼 오버플로우 공격
- 프로그램 실행 시 동적으로 할당되는 힙 영역에 할당된 버퍼 크기를 초과하는 데이터(실행 가능 코드)를 입력하여 메모리의 데이터와 함수 주소 등을 변경, 공격자가 원하는 임의의 코드를 실행하는 공격 기법
- 인정합 메모리(Linked-List)의 데이터가 삭제될 수 있으며, 해당 위치에 특정 함수에 대한 포인터 주소가 있으면 이를 악용하여 관리자 권한 파일에 접근하거나, 공격자의 특정 코드를 실행함



### 버퍼 오버플로우 공격 대응방안
(1) 스택가드 활용
- 카나리라고 불리는 무결성 체크용 값을 복귀 주소와 변수 사이에 삽입해 두고, 버퍼 오버플로우 발생 시 카나리 값을 체크, 변할 경우 복귀 주소를 호출하지 않는 방식으로 대응

(2) 스택쉴드 활용
- 함수 시작 시 복귀 주소를 Global RET라는 특수 스택에 저장해 두고, 함수 종료 시 저장된 값과 스택의 RET 값을 비교해서 다를 경우 오버플로우로 간주하고 프로그램 실행을 중단

(3) ASLR(Address Space Layout Randomization) 활용
- 메모리 공격을 방어하기 위해 주소 공간 배치를 난수화하고, 실행 시마다 메모리 주소를 변경시켜 버퍼 오버플로우를 통한 특정 주소 호출을 차단
- 리눅스에서 설정 가능

(4) 안전한 함수 활용
- 버퍼 오버플로우에 취약한 함수: strcat(), strcpy(), gets(), scanf(), sscanf(), vscanf(), vsscanf(), sprintf(), vsprintf()
- 버퍼 오버플로우에 안전한 함수: strncat(), strncpy(), fgets(), fscanf(), vfscanf(), snprintf(), vsnprintf()

(5) 실행 제한
- 스택에서의 쓰기 권한 제한
- 스택에서의 프로그램 실행 금지
- 가능성이 있는 SUID 프로그램 제한



### 형상 관리의 절차
- 형상 관리는 소프트웨어 개발을 위한 전체 과정에서 발생하는 모든 항목의 변경 사항을 관리하기 위한 활동이다
- SW 생명 주기 동안 형상 관리를 통해 산출물을 체계적으로 관리하여 SW의 가시성, 추적성, 무결성 등의 품질 보증을 보장할 수 있다.

(1) 형상 식별
- 형상 관리 대상을 정의 및 식별하는 활동
- 추적성 부여를 위해 ID와 관리번호를 부여
- 변경 관련 이슈 발생 시 ID와 관리번호를 이용하여 추적

(2) 형상 통제
- 형상 항목의 버전 관리를 위한 형상통제위원회 운영
- 변경요구 관리, 변경제어, 형상 관리 등 통제 지원
- 베이스라인에 대한 관리 및 형상 통제 수행 가능

(3) 형상 감사
- 소프트웨어 베이스라인의 무결성 평가
- 베이스라인 변경 시 요구사항과 일치 여부 검토

(4) 형상 기록
- 소프트웨어 형상 및 변경관리에 대한 각종 수행결과를 기록
- 형상결과 보고서 작성



### 병행제어 미보장 시 문제점
(1) 갱신 손실(Lost Update)
- 먼저 실행된 트랜잭션의 결과를 나중에 실행된 트랜잭션이 덮어쓸 때 발생하는 오류

(2) 현황 파악오류(Dirty Read)
- 트랜잭션의 중간 수행 결과를 다른 트랜잭션이 참조하여 발생하는 오류

(3) 모순성(Incosistency)
- 두 트랜잭션이 동시에 실행되어 데이터베이스의 일관성이 결여되는 오류

(4) 연쇄복귀(Cascading Rollback)
- 복수의 트랜잭션이 데이터 공유 시 특정 트랜잭션이 처리를 취소할 경우 트랜잭션이 처리한 곳의 부분을 취소하지 못하는 오류


### 라우팅 프로토콜
(1) RIP(Routing Information Protocol)
- AS(Autonomous System, 자치 시스템, 자율 시스템) 내에서 사용하는 거리 벡터 알고리즘에 기초하여 개발된 내부 라우팅 프로토콜
- 거리 벡터 라우팅 기반 메트릭(Metric) 정보를 인접 라우터와 주기적으로 교환하여 라우팅 테이블을 갱신하고 라우팅 테이블을 구성/계산하는 데 Bellman-Ford 알고리즘을 사용하는 내부 라우팅 알고리즘
- 최대 홉 수(Hop Count)를 15개로 제한
- 사용 포트로는 UPD를 사용(UDP 포트 번호 520 사용)
- 30초마다 전체 라우팅 정보를 브로드캐스팅

(2) OSPF
- 규모가 크고 복잡한 TCP/IP 네트워크에서 RIP의 단점을 개선하기 위해 자신을 기준으로 링크 상태 알고리즘을 적용하여 최단 경로를 찾는 라우팅 프로토콜
- 링크 상태 라우팅 기반 메트릭 정보를 한 지역 내 모든 라우터에 변경이 발생했을 때만 보내(Flooding)고 라우팅 테이블을 구성/계산하는 데 다익스트라 알고리즘을 사용하는 내부 라우팅 프로토콜
- 최소 지연, 최대 처리량 등 관리자가 라우팅 메트릭 지정
- AS를 지역으로 나누어 라우팅을 효과적으로 관리 가능
- 홉 카운트에 제한이 없음

(3) BGP
- 자치 시스템(AS) 상호 간(Inter-AS 또는 Inter-Domain)에 경로 정보를 교환하기 위한 라우팅 프로토콜
- 변경 발생 시 대상까지의 가장 짧은 경로를 경로 벡터(Path Vector) 알고리즘을 통해 선정하고, TCP 연결(port 179)을 통해 자치 시스템(AS)으로 라우팅 정보를 신뢰성 있게 전달
- ISP 사업자들 상호 간에 주로 사용되는 라우팅 프로토콜
- 순환을 피할 수 있도록 목적지까지 가는 경로 정보를 제공
- 라우팅 비용(CPU 부하)이 크고, 라우팅 테이블의 크기가 커서 메모리 사용량이 많음



### 정보처리기사 3회 출제 문제
출처: https://www.gisafirst.com/board/n1/view.php?offset=0&tq=1393907668&reqCategory=&idx=413&word=&s_type=&s_content=&s_terms=

1. 싱글톤 패턴을 자바로 구현한 실행 결과
- 답안: 3

2. MAC 주소를 가로채는 공격: (    ) Spoofing
- 답안: ARP

3. 데이터 제어어(DCL) 중 GRANT 에 대한 개념 서술
- 답안: 사용자에게 권한 부여

4. AAA 서버의 각 A에 해당 되는 개념을 풀어써주고 맞는 용어를 매핑 시키는 문제
신분을 확인하는 인증(authentication), 접근·허가를 결정하는 인가(authorization), 리소스 사용정보를 수집·관리하는 계정(accounting)을 통합한 보안소프트웨어로, 3A라고도 함
- 답안: Authentication, Authorization, Accounting

5. 디자인 패턴
- 답안: Factory Method

6. 결합도(coupling) 종류 중 단순 처리할 대상인 값만 전달되는 게 아니라 어떻게 처리를 해야 한다는 제어 요소가 전달되는 경우이다
- 답안: Control

7. C언어 구조체
- 답안: 501

8. 하위 모듈에서 시작한다는 ( ) 테스트로, 하위 모듈들을 포괄하는 ( )이 있어야 함.
보기가 있는 문제.
- 답안: 상향식 통합, 드라이버

9. 파이썬 실행 결과
a, b = 100, 200
print( a == b )
- 답안: False

10. SQL Cross Join Count
- 답안: 4

11. 데이터 접근 방식. <값, 주소>. 한 단어로 쓰시오
- 답안: Index(또는 인덱스)

12. 테스트 케이스 관련 표를 보여주고 컬럼 제목란에 해당 되는 내용 매핑하기
- 답안: 테스트 조건, 테스트 데이터, 예상 결과

13. UML 종류 중 ( ) 다이어그램 설명해 주고 빈칸 넣기. 속성, 메소드 포함됨
- 답안: 클래스

14. OSI 7 Layer 중 3개 계층 설명 후 해당하는 계층
- 답안: 데이터 링크, 네트워크, 프레젠테이션

15. 암호화 기법, 64비트, IBM, 16라운드
- 답안: DES

16. C 포인터
- 답안: 37

17. 자바 조건문 처리 후 a 출력
- 답안: 7

18. 입력 자료 간의 관계와 출력에 영향을 미치는 상황을 체계적으로 분석 후 효용성이 높은 테스트 케이스를 선정해서 테스트하는 기법
- 답안: Cause Effect Graph

19. 사용자가 키보드, 마우스 등을 이용...  인터페이스. 유저 인터페이스로 윈도우, 맥킨토시 등이 있다. 
- 답안: GUI

20. 관계 - 집합, 상속(일반화)
- 답안: Aggregation, Generalization

