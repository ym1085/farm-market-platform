# farm-market Bruno 컬렉션

Bruno의 Open Collection에서 이 `bruno` 디렉터리를 선택한다
기존 개인 컬렉션의 요청 5개를 YAML 형식으로 복사했다

## 사용 순서

1. API 서버를 실행한다
2. Bruno에서 `local` 환경을 선택한다
3. 환경 설정에서 사용할 계정의 `email`, `password`를 Secret 값으로 입력한다
4. 회원가입에는 `memberName`, `phoneNumber`도 입력한다
5. 로그아웃·토큰 재발급에는 로그인 응답의 토큰을 `refreshToken` Secret 값으로 입력한다

기본 서버 주소는 기존 요청의 `http://localhost:8080`이다
실행 환경이 다르면 `baseUrl`을 변경한다
요청은 기존 컬렉션에서 가져왔으며 현재 서버와의 호출 검증은 별도로 수행해야 한다

## 구조와 Git 관리

- `opencollection.yml`: 컬렉션 이름과 설정
- `environments/local.yml`: 서버 주소와 Secret 변수 선언
- `[주문] 상품 정보/`: 상품 조회 요청
- `[회원] 회원 정보/`: 회원가입·로그인·로그아웃·토큰 재발급 요청

Bruno에서 저장하면 이 디렉터리의 파일이 변경된다
API 코드와 요청 파일을 함께 리뷰하고 커밋한다
계정 정보와 토큰은 Secret 값으로 입력하고 요청 본문에 직접 저장하지 않는다
기존 Documents의 개인 컬렉션은 별도 복사본이므로 이후에는 이 컬렉션을 사용한다
