# 4주차 회고  
기간: 2022. 4. 10.  ~ 4. 16.

## 사실 Fact
### 알게 된 것
- [클린 아키텍처](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html): 소프트웨어 계층을 분리, 관심사를 분리하는 아키텍처. 테스트와 유지보수에 용이.
- Entity: 객체지향에서 식별자를 가진 객체를 뜻함. 
- Repository: 데이터에 접근하는 것을 캡슐화.
- [JPA](https://spring.io/projects/spring-data-jpa): 자바 ORM(Object-Relational Mapping) 기술 표준

### 익힌 것
- Springboot Repository 사용법, CrudRepository를 사용하면 더 간단히 구현 가능
- JPA 사용법
- H2 Database 사용법

## 느낌 Feeling
- 이직 때문에 정신이 없어서 과제를 끝내는데 너무 급급했다.
- 아직 테스트가 익숙하지 않다. 명확하게 이해를 못했다. 좀 더 살펴봐야겠다.

## 교훈 Finding
- 단순히 커버리지를 채우는 게 아니라 테스트를 왜 하는지, 테스트 목표가 무엇인지 살펴봐야겠다는 생각이 들었다.

## 피드백 Feedback
### [코드 리뷰](https://github.com/CodeSoom/spring-week4-assignment-1/pull/60) - by johngrib님 
- 기왕 하는 김에 용도를 나누어 조회용과 변경용 서비스로 분리해 봅시다. 지금은 서비스 사이즈가 작아 이 정도로도 충분해 보이지만, 조회 메소드와 업데이트 메소드가 용도별로 쭉쭉 늘어나는 건 흔한 일이죠. 조회 전용 서비스가 나뉘어 있기만 해도 상대적으로 복잡도를 관리하기 용이할 거에요.
- import *의 사용을 지양해 주세요.
- 한 줄에 . 이 하나씩만 오게 개행해보세요.
- 컨트롤러의 기능에 대해 생각해 보세요. 컨트롤러를 어떻게 테스트하는 것이 바람직할까요? 이렇게 테스트하면 컨트롤러의 역할의 일부만 확인할 수 있습니다.
- 이 테스트는 productService.getProduct가 productRepository의 findById를 호출하는지를 검사하고 있습니다. 그런데 이건 이 테스트의 목표가 아닐 겁니다. 이 테스트의 진짜 목표는 무엇일까요?
