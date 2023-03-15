# 1주차

# 웹 기초 교육

## 웹

- 사용자끼리 연결된 망
- 사용자들이 서로의 정보를 공유할 수 있는 공간

## 웹의 특징

하이퍼텍스트를 연결하여 멀티미디어 정보 제공

- 물리적 웹 서버
  - 하드웨어(컴퓨터)
- 소프트웨어적 웹 서버
  - 클라이언트가 요청을 보냈을 때, 응답을 주는 서버(HTTP 메소드를 이용)
  - 요청을 받으면 html 파일을 전송
  - HTTP: html 파일을 보내주기 위한 프로토콜

## HTTP

- 인터넷에서 데이터를 주고받을 수 있는 프로토콜
- url: 주소, uri: 식별자
- 사용자마다 html 파일을 동적으로 만들어 보냄
- CGI를 이용해 동적인 페이지를 만들 수 있음 ⇒ 컨테이너 (요즘에는 php 등을 씀)
- http 프로토콜 ⇒ stateless: 연결을 유지하지 않고 상태를 유지하지 않음

## 로그인 방식

### 1. 세션 & 쿠키

**과정**

- 클라이언트에서 로그인을 해서 아이디와 비밀번호를 서버에 전달하고
- 서버가 사용자를 인증하고, 인증된 사용자에게 세션 아이디를 부여하며, 헤더에 쿠키를 담아서 응답을 보냄,
- 클라이언트는 그 쿠키를 로컬에 저장. 매 응답 시 쿠키를 헤더에 담아서 보냄

**단점**

- 유효 기간이 지나지 않은 이상 서버에 세션을 저장하고 있어야 하기 때문에 서버에 부담

### 2. 토큰

- 세션과는 달리 서버가 사용자의 정보를 가지고 있지 않고 토큰에 담긴 정보를 통해 사용자 인증

**과정**

- 암호화 기법을 사용한 토큰을 만들어서 클라이언트에게 전송
- 사용자는 매 응답 시 토큰을 헤더에 담아 전송
- 토큰에는 정보가 담겨 있어, 서버가 정보를 통해 사용자를 인증

**단점**

- 탈취되면 위험하기 때문에 자주 리프레시 해야함

## 프론트엔드가 나눠진 이유

- 서버가 모든 역할을 하기에는 부하가 심하여 화면 구성 등과 같은 기능을 나눔
- csr, ssr: 서버는 api만 제공하고 클라이언트가 해당 api를 불러와 사용

### 참고

- 와쓰 ⇒ django, spring과 유사
- 스레드, 프로세스
