## 1. HTTP method의 용도에 대해 간단히 설명하시오.
http 의 메소드에는 get post head 등 여러 가지 메소드가 있다. 
그 중 수업시간에 강조하신 get 과 post에 대해  간단히 설명하면 
get은 요청받은 URL의 정보를 검색하여 응답한다. 
post는 요청된 자원을 create한다.

## 2. 동규는 Spring Controller 메소드의 리턴 값이 “users/login” 인 것과 “redirect:/users/login”의 동작이 다른 것을 발견하였다. 어떤 차이가 있는지와 용도에 대해 설명하시오. 

/users/login은 templates 내 users/login을 응답으로 반환한다.
redirect:/users/login은 클라이언트가 서버의 /users/login url로 재요청을 하도록 한다.


## 3. Spring의 DI/IoC란 무엇인가? 지난 실습에서 사용한 적이 있는가?

IoC = DI + DL + ...
IoC(Inverse of Control) :  제어의 역전, 모든 종류의 작업을 사용하는 쪽에서 제어하는 구조 
DI(Dependency Injection) : 의존성 주입, 각 계층 사이, 각 클래스 사이에 필요로 하는 의존 관계를 컨테이너가 자동으로 연결해줌. 
DL (Dependency Lookup) : 저장소에 저장되어 있는 Bean에 접근하기 위해서, 개발자들이 컨테이너에서 제공하는 API를 이용하여 사용하고자 하는 Bean을 Look Up하는 것

IoC. Spring에서 우리가 필요한 controller, service, DAO 등을 대신 생성하여 관리하고 있으므로 IoC 적용 중.
DI. @Autowired annotation을 통해서 DI를 함.

ref. 
http://javaplant.tistory.com/18
http://isstory83.tistory.com/91
