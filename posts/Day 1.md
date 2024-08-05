네트워크 기초
======================
## 1. HTTP/HTTPS
### 1.1 HTTP
* 평문으로 통신, 데이터 변조 가능성
### 1.2 HTTPS
* HTTP에 암호화, 인증기능 추가

## 2. TCP/IP/UDP/Port
### 2.1 TCP
* 3 way handshake
* 데이터 전달 보증
* 순서 보장
* IP의 단점 보완
### 2.2 IP
* 패킷 단위로 전송
* 비신뢰성으로 패킷 전송을 보장하지 않음
* 패킷 조각화로 인한 성능 저하 또는 오류
### 2.3 UDP
* 단순해서 성능 좋음
* HTTP2, HTTP3에서 사용
* IP와 거의 유사하나 PORT, Checksum 추가
### 2.4 Port
* 단일 IP 주소에서 여러 서비스를 동시에 실행하거나 식별의 용이성을 위해 존재
* HTTP:80, HTTPS:443 등 정해진 포트가 있음

TCP/IP 패킷 정보

<img src="/posts/img/pa1.png" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="pa1"></img><br/>

3 way handshake

<img src="/posts/img/3way.png" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="3way"></img><br/>


## 3. DNS/URI/URL
### 3.1 DNS
* 외우기 힘든 IP 주소를 대신함
* DNS 서버와 통신해 IP 주소와 변환
### 3.2 URI
* URL (locator) + URN (name) = URI
### 3.3 URL
```
https://www.google.com/search?q=calendar&oq=calendar&sourceid=chrome&ie=UTF-8
```
	1. 프로토콜 	(https)
	2. 호스트명 	(www.google.com)
	3. port 	(생략)
	4. path     	(/search)
	5. 쿼리 파라미터 (q=calendar&ie=UTF-8)
 
### 3.3.1 쿼리 파라미터
* ? 뒤에 오는 값 key=value
* key, value 값으로 string 데이터를 전달해 쿼리 스트링으로도 볼림

## 4. 웹 브라우저 요청 흐름

	1. URL 입력 -> DNS로 IP 조회 후 해당 주소로 HTTP 요청 메시지 전송
	2. 브라우저가 HTTP 메시지 생성
	3. Socket 라이브러리를 통해 전달
	4. TCP/IP 패킷 생성 (HTTP 메시지 데이터 포함)

### 4.1 패킷 전달 과정

	1. 요청 패킷 전달
	2. 응답 패킷 전달
	3. 응답 패킷 도착 / 웹 브라우저 렌더링

패킷 구조는 다음과 같다

<img src="/posts/img/packet.png" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="packet"></img><br/>

## 5. HTTP 상태코드

- 1xx : 정보(Information) : 요청을 받아들여 처리중
- 2xx : 성공(Successful) : 요청을 정상적으로 처리했음
- 3xx : 리다이렉트(Redirection) : 요청을 완료하기 위해서 추가 동작이 필요
- 4xx : 클라이언트 오류(Client Error) : 서버는 요청을 이해 불가능
- 5xx : 서버 오류(Server Error) : 서버는 요청을 처리 실패
