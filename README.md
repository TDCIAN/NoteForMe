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
  - 요청 헤더의 Content-Length를 비정상적으로 크게 설정하여 메시지 바디 부문을 매우 소량으로 보내 계속 연결 상태를 유지시키는 공ㄱㄱ

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
- 요구사항을 충족시켜주지 못한다면, 결함이 없다고 해도 품질이 
