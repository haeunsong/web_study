## 토큰 기반의 인증 시스템

- 인증받은 사용자들에게 토큰을 발급하고, 서버에 요청을 할 때 헤더에 토큰을 함께 보내도록 하여 유효성 검사를 한다.
- 이렇게 하면 더이상 사용자의 인증 정보를 서버나 세션에 유지하지 않고 클라이언트 측에서 들어오는 요청만으로 작업을 처리한다.
- 즉, 서버 기반의 인증 시스템과 달리 상태를 유지하지 않으므로 Stateless 한 구조를 갖는다.

- 순서
1. 사용자가 아이디와 비밀번호로 로그인을 한다.
2. 서버 측에서 해당 정보를 검증한다.
3. 정보가 정확하다면 서버 측에서 사용자에게 Signed 토큰을 발급한다. (Signed는 해당 토큰이 서버에서 정상적으로 발급된 토큰임을 증명하는 Signature를 가지고 있다는 것)
4. 클라이언트 측에서 전달받는 토큰을 저장해두고, 서버에 요청을 할 때마다 해당 토큰을 서버에 함께 전달한다.
이 때, HTTP 요청 헤더에 토큰을 포함시킨다.
5. 서버는 토큰을 검증하고, 요청에 응답한다.

## 서버 기반의 인증 시스템

- 시스템의 규모가 커질 경우 문제가 생겨서 토큰 기반 방식이 등장함)
- 서버 측에서 사용자들의 정보를 기억하고 있어야 한다.
- 사용자들의 정보를 기억하기 위해서는 세션을 유지해야 하는데, 메모리나 디스크 또는 데이터베이스 등을 통해 관리한다.
- Sateful 서버. 클리어언트로부터 요청을 받으면, 클라이언트의 상태를 계속해거 유지하고 이 정보를 서비스에 이용.
- 사용자가 로그인을 하면, 세션에 사용자 정보를 저장해두고 서비스를 제공할 때 사용한다.

cf. mangkyu.tistory.com/55
+ JWT(Json Web Token)
