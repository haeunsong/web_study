# JWT(Json Web Token)
- 토큰 기반 인증 방식
- 사용자의 세션 상태를 저장하는 것이 아니라 필요한 정보를 토큰 body에 저장해 사용자가 가지고 있고
  그것을 증명서처럼 사용함.
- 사용자는 Access Token(JWT Token)을 헤더에 실어 서버로 보냄.

## 토큰을 만들기 위해서 필요한 것(Header, Payload, Verify Signature)
* Header
  * Header, Payload, Verify Signature 정보를 암호화할 방식(alg), 타입(type) 등이 들어감.
* Payload
  * 서버에서 보낼 데이터가 들어감.
  * 일반적으로 사용자의 ID, 유효기간이 포함
  * 클라이언트에 대한 정보, META data 같은 내용이 들어있고, Base64로 인코딩 되어있음.
*Verify Signature
  * Base64로 인코딩한 Header, Payload, SECRET KEY를 더한 후 서명됨.

----> 최종적인 형태
: Encoded Header.Encoded Payload.Verify Signature(xxxx.yyyy.zzzz)

## JWT 인증 방식
1. 클라이언트가 로그인을 위해 해당 정보를 서버에 전달
2. 서버는 전달된 데이터로 사용자를 확인하고 사용자의 고유한 ID값을 부여한 후, 기타 필요한 정보와 함께 payload에 추가
3. JWT토큰의 유효기간을 설정
4. 암호화할 SECRET KEY를 이용해 Access Token을 발급
5. 사용자는 Access Token을 받아 저장한 후, 인증이 필요한 요청마다 토큰을 헤더에 추가하여 전달
6. 서버에서는 해당 토큰의 Verify Signature를 SECRET KEY로 복호화한 후, 조작여부, 유효기간을 확인
7. 해당 토큰이 유효하면 Payload를 디코딩하여 사용자의 ID에 맞는 데이터를 호출

### 세션/쿠키 방식과의 차이점
: 세션/쿠키는 세션 저장소에 유저의 정보를 넣지만, JWT는 토큰 안에 유저의 정보를 넣는다.
사용자 입장에서는 헤더에 세션ID나 토큰을 실어서 보내준다는 점에서는 동일하지만, 
서버 측에서는 인증을 위해 암호화를 하냐, 별도의 저장소를 이용하냐의 차이 발생.

## 장점
- JWT는 발급한 후 토큰 검증만 하면 되기 때문에 추가 저장소가 필요없음.
- 서버 확장, 유지, 보수에 유리
- 토큰 기반의 다른 인증 시스템에 접근 가능

## 단점
- 세션/쿠키의 경우 세션 ID가 변질되면 해당 세션을 지우면 되지만, JWT는 한 번 발급되면 유효기간이 완료될 때까지 계속 사용 가능하므로
정보 탈취 가능성 존재.(보안성 낮음)
- payload 정보가 제한적 payload는 따로 암호화되지 않기 때문에 디코딩하면 누구나 정보를 확인할 수 있어서 담는 데이터가 제한적임.
- 세션/쿠키 방식에 비해 JWT의 길이가 길어서 인증이 필요한 요청이 많아질수록 서버 자원낭비 발생.

cf. Refresh Token 
