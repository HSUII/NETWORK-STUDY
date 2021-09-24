# HTTP2

## HTTP2란?

HTTP2는 WWW에서 쓰이는 HTTP 프로토콜 두번쨰 버전이다. 
HTTP1.1과 호환성은 유지하면서 다양한 기능을 추가해서 더 나은 HHTP 프로토콜을 구현하는 것을 목표로 하였다. 

## 목표

- HTTP 헤더 데이터 압축
- 서버 푸시 기술 
- 요청을 HTTP 파이프라인으로 처리 
- HTTP1의 HOL blocking 문제 해결 
- TCP 연결하나로 여러 요청을 다중화 처리
- 데스크탑, 모바일 브라우저, 웹 API, 웹 서버, 프록시 서버, 방화벽 등 자주 사용되는것들을 지원 

## 지원되는 브라우저 

크롬, IOS용 크롬, 파이어폭스 익스플로러11, MICROSOFT EDGE, 오페라, 사파리9 

***

## HTTP2 CHECKER 

HTTP2를 사용하기 위해선 클라이언트와 서버 양측 모두 HTTP/2를 지원해야 한다. 
지원 여부를 파악히기위해 HTTP/2 CHEKCER 프로그램을 사용해 서버에게 HTTP/2를 지원하는지를 질의하고 ,    
그에 대한 응답여부에 따라 HTTP/2로 통신해야할지, HTTP1.1으로 통신해야할지 경정해야한다

### CHECKER 방식 

RFC7540에 통신 방법이 정의되어있다. 

클라이언트가 최초 서버 접속시 Upgrade,HTTP-2 Settings 헤더를 요청 헤더에 실어 보낸다. 
HTTP2-Settings 커스텀 헤더는 각종 연결에 필요한 설정 정보를 base64url 인코딩한 값이다. 
![image](https://user-images.githubusercontent.com/87008955/132651279-8dbb2a91-2966-425e-8cf0-41018d247b1a.png)

**서버가 HTTP/2를 지원하지 않는다면, 요청에 대한 응답을 HTTP1.1버전의 200 OK로 응답한다.**     

![image](https://user-images.githubusercontent.com/87008955/132651467-bb1e810b-bc00-49de-900f-b895ba51629d.png)

**서버가 HTTP/2를 지원한다면 101 Swotoching Protocols 응답을 한다**
그리고 프로토콜이 업데이트 가능함을 Connection 헤더로 알려주고, Upgrade 헤더에 HTTP/2 지사자인 h2c로 응답한다. 

![image](https://user-images.githubusercontent.com/87008955/132651753-f599ea09-9f3f-4a8b-8f7d-0d78c2c3d0b2.png)


출처: <https://www.popit.kr/http2-rfc%EB%A5%BC-%EC%9D%91%EC%9A%A9%ED%95%9C-http2-checker%EC%9D%98-%EA%B5%AC%ED%98%84/>
