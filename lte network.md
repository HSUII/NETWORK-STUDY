# 네트워크 구조 기초 

## LTE
: 4G 이동통신기술을 의미하며 , Long Term Evolution 문자 그대로 장기간에 걸쳐 기존시스템을 발전시킨 기술이라는 의미를 포함하고 있다.   
- LTE 특징
: 3G 이동통신과 구별되는 가장 큰 특징은 100Mbps~최대 1Gpbs를 지원하는 빠른 속도이다. 

- LTE 네트워크 구조 
- ![image](https://user-images.githubusercontent.com/87008955/127414554-745a78e5-5f0a-48da-8c09-68b1bdf2e41b.png)

: LTE를 구성하는 네트워크 장비요소들이다. 
< 용어 설명 > 

-	UE: 사용자 단말로 IMSI값으로 식별한다.
-	eNB: LTE 기지국, LTE네트워크 간에 무선연결을 제공하는 장비 
-	S-GW: 핸드오버 시 앵커 역할, 
-	P-GW: 1)단말에 IP 주소 할당 2)S-GW에 대한 앵커 수행 3)UE별로 Accounting Data 관리
-	MME: 1)UE 인증 2)EPS 베어러 관리 3)가입자 위치, 인증 관리 
-	HSS: 가입자 별로 KEY,프로파일 갖고있는 DB
-	PCRF: UE별로 정책과 과금에 대한 규칙을 정하는 장비 
-	SPR: 정책 룰을 저장하고있는 DB
-	OCS: 선불제 사용하고 있는 사용자를 관리하는 시스템
-	OFCS: P-GW가 전달해주는 CDR을 받아 중앙에서 관리하는 장비 
-	PDN: 인터넷
-	IMS : IP를 기반으로 음성, 오디오, 비디오 등의 멀티미디어 서비스를 제공하는 규격, VoLTE서비스를 제공해준다. 

- LTE 음성통화 VoLTE
    - 기존의 3G는 음성 서비스 (CIRCUIT SWITHING) 방식으로 통화를 지원했지만 4G LTE에서는 PACKET SWITCHING 방식으로 통화를 지원한다. 
    - LTE를 통해 음성서비스를 제공하는 것을 **VoLTE**라고 한다. 인터넷접속하는 데이터 서비스와 음성 서비스 모두 lte로 이루어지지만, 음성서비스의 경우 끊기거나 , 지연되면 
안되기 떄문에 두 lte를 분리해서 따로 IP를 제공해서 서비스한다.   
    - 두 IP 중 하나는 인터넷 접속용이고, 다른 IP는 VoLTE를 위한 IMS 전용 IP로 사용하게 된다. 
    ![image](https://user-images.githubusercontent.com/87008955/127415454-27e2d5c6-b9bc-4886-8891-f43cb17f3014.png)
***
- **DIATMETER PROTOCOL**   
: 이동 인터넷 및 모바일 IP 가입자에게 로밍서비스를 제공하기 위해서 요구도는 AAA(Authentication Authorization, Accounting) 기술 중에서 최근에 제안되고 있는 정보 보호 기술이다.   
  기존 프로토콜의 한계점 극복, 로밍에 필요한 도메인 간 이동성 지원, 강화된 보안 제공, 보안 및 신뢰성을 기반으로 하는 하부 프로토콜 수용, 미래 서비스를 수용할 수 있는 유용한 확장성 등 특징을 가지고 있다.    
  4G LTE에 적용하는 주요 기술이다.
  - **DRA(DIAMETER ROUTING AGENT)**   
  : DIAMAETER 메세지를 라우팅 하는 시스템이며, DIAMETER 네트워크의 효율적인 관리 및 유용한 증설, 망 구성을 제공하는 시스템이다. 
    DRA를 도입하면 시스템 별 국 데이터 변경없이 DRA 자체 국 데이터 변경 만으로 망 운용이 가능하며, 망 장애 발생시 우회경로 제공 및 국사이원화 구조를 제공한다.    
      또한 망 관리의 편리성을 제공함으로, 복잡해지는 네트워크의 구성을 단순화 할 수 있다. 
      <주요 기능>
      - RELAY 기능 
      - PROXY 기능
      - PCRF SELECTION 및 SESSION BINDING
      - ADDRESS RESOLUTION 및 LOAD BALANCING
      - DRA-DRA 
  
