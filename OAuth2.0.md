# OAuth2.0
- 각종 웹, 모바일 어플리케이션에서 타사의 API를 이용하고 싶을 때 권한 획들을 위한 프로토콜
- ex> "facebook으로 로그인", "Google 계정으로 로그인", "Naver로 로그인" 
- 사용하려는 서비스마다 회원가입을 할 필요없이 기존의 사용하던 타사의 정보를 이용하여 로그인 가능

## Authentication(인증) vs Authorization(허가)
- 일반 로그인은 회원가입할 때 사용했던 아이디와 비번을 통해 '인증'을 받지만,
- OAuth2.0은 타사 서비스의 이메일 정보에 우리가 만든 서비스의 접근을 '허락'하여 사용자를 인증한다.

### 용어
Client: 사용자가 사용하려는 우리가 만든 서비스.
Resource Server: 서비스에 자신의 API를 제공하는 타사 서비스.
Resource Owner: 우리가 만든 서비스를 타사 서비스를 통해 이용하려는 사용자.

## 과정
1. client가 Resource Server의 API를 사용한다고 Resource Server에 등록을 해야한다.
2. 그렇다면 Resource Server는 이 Client를 식별할 수 있는 Client ID와 Client Secret을 발급한다.
3. 이 후 사용자(R.O)가 우리가 만든 Client에서 Google 계정으로(ex) 로그인을 통해 로그인을 요청한다.
4. client는 사용자에게 Resource Server의 로그인 창을 띄어준다.
5. 사용자는 client가 'Resource Server에 있는 자신의 정보에 접근에 대한 동의'를 구하는 창을 보고 동의를 한다.
6. 사용자(R.O)가 Resource Server에 등록되어있는 자신의 정보를 사용가능하도록 클라이언트(client)에게 허락하면, 
Resource Server는 client에게 일련의 암호화된 코드를 제공하고 이 코드와 함게 해당정보의 사용등록을 했는지 여부를 판단하는 
Client Id와 Client Secret을 함께 보내, 모든 것이 일치한다면 최종 접근 권한 부여의 암호인 'Access Token'을 발급한다.



