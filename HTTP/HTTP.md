# HTTP

HTTP는 웹 서버와 클라이언트 간의 통신 규약을 의미한다. 

주소창에 URI를 입력해 서버에게 정보를 요청하면, 클라이언트가 해당 정보를 받게 된다. 이떄 클라이언트와 서버간의 포로토콜이 HTTP이다. 

클라이언트의 요청은 HTTP Request, 서버의 응답은 HTTP Response라고 한다. 
이때 정보는 HTML뿐만 아니라 JSON,XML등 다양한 형태로 받을 수 있다. 

## TCP/IP

HTTP는 TCP/IP 프로토콜을 사용해서 패킷 통신을 한다. 
TCP는 도착한 조각을 점검하고 잘못된 조각을 다시 요청하는 역할을 하며,    
IP는 데이터 조각을 최대한 빨리 목적지로 보내는 역할을 한다.    

## HTTP의 진화 

1) HTTP/0.9

HTTP의 초기번전으로 원래는 버전 번호가 없었지만, 이후 버전과 구분하기 위해 0.9로 불리게 되었다. 
요청은 단일 라인으로 구성되며, GET 메서드만 사용가능하다 

2)HTTP/1.0 

초기버전을 확장한 버전으로 버전정보가 각 요청 사이로 함께 전송되기 시작했다.    
또한, 브라우저 요청에 대한 결과를 알 수 있게 되었고, 그 결과에 대한 동작을 구현할 수 있게 되었다.   
1.0때 HTTP header가 도입되었다. 

3)HTTP/1.1 

HTTP의 첫번째 표준 버전으로 1.0에 비해 많은 개선 사항이 도입되었다. 
한 커넥션에서 여러개의 메세지를 동시에 주고받을 수 있기 때문에 속도가 훨씬 빠르다. 

## HTTP 메세지 

1) Request/요청 메세지 

```
POST http://naver.com/1.1  // = 시작줄 / ﻿HTTP Method, Request target, HTTP Version
Host : localhost:8000
user-Agent : Mozilla/5.0 ...  // = header 
-12656974
(more data)..  // = body
```

첫줄에는 HTTP 메소드 ,요청 타겟, HTTP 버전이 들어간다. 
Header는 요청에 대한 추가 정보를 담고 있는 부분이다. 공통헤더, 요청헤더, 응답헤더로 나뉘며 다양한 종류의 header가 존재한다. 

마지막으로 body 본문은 업데이트할 때 사용되며 반드시 필수사항은 아니다. 

- HTTP Method 

![image](https://user-images.githubusercontent.com/87008955/134633002-a3f5ea9c-5f09-46e9-a07f-60c0d9c34305.png)

- header 

![image](https://user-images.githubusercontent.com/87008955/134633054-8386b9ca-449f-4661-a994-4fed506af567.png)

2)Response/응답 

```
HTTP/1.1 200 OK  // = 시작줄 / HTTP 버전, 상태코드, 상태 텍스트
Access-Control-Allow-Origin : *
Connection : Keey-Alive  //header
<!DOCTYPE html><html lang="ko" data-reactroot=""><h...  //body
```

Response는 서버에서 받은 응답을 뜻한다.    
HTTP메세지는 요청과 똑같이 시작줄, header,body로 이루어져있다. 



[출처: 프론트엔드 면접 질문 정리, HTTP & HTTPS (feat. HTTP/1.1, HTTP/2.0, HTTP Method)|작성자 Jaeeun](https://blog.naver.com/jaeeun_98/222458024463)
