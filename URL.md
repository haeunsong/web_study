# http://www.example.com:80/path/to/myfile.html?key1=value1&key2=value2#SomewhereInTheDocument

## http 
- 브라우저가 사용해야하는 프로토콜.
- 프로토콜은 컴퓨터 네트워크에서 데이터를 교환하거나 전송하기위한 설정방법이다.
- 일반적으로 http, 보안버전 https를 사용한다.
- 하지만 mailto: 와 같은 다른 방법도 있음.

## www.example.com
- 도메인 이름. 요청중인 웹서버.
- .com -> TLD
- .example -> 2차레벨 도메인(SLD)

## :80 (우편번호같은 역할..?)
- 포트. 웹서버의 리소스에 액세스하는데 사용되는 기술 "게이트"를 나타냄.
- 웹서버가  HTTP 프로토콜의 표준 포트 (HTTP의 경우 80, HTTPS의 경우 443)를 사용하여 자원에 대한 액세스 권한을 부여하는 경우 일반적으로 생략.
  그렇지 않으면 필수.
  
## /path/to/myfile.html
- 웹서버의 자원에 대한 경로. 

## ?key1=value1&key2=value2
- 웹서버에 제공되는 추가 매개변수.
- &기호로 구분된 키/값 쌍의 목록임. 웹서버는 이를 이용하여 리소스를 반환하기 전에 추가작업 수행가능.
- (물음표 뒷부분을 쿼리문자열 이라고도 하는 것 같다..)

## #SomewhereInTheDocument
- 리소스 자체의 다른 부분에 대한 앵커(책갈피).
- 프래그먼트 식별자 라고도 하는 # 다음의 부분 은 절대로 요청과 함께 서버로 전송되지 않는다.

  
