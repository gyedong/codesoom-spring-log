# 5주차 회고  
기간: 2022. 4. 17.  ~ 4. 23.

## 사실 Fact
### 알게 된 것
- [Java Validation](https://docs.oracle.com/javaee/7/tutorial/bean-validation001.htm): 자바 유효성 검사
- [Lombok](https://projectlombok.org/): getter나 setter처럼 반복적으로 만들어야 하는 것을 자동으로 만들어주는 라이브러리
- [Dozer](https://dozermapper.github.io/): 객체 맵퍼 

### 익힌 것
- Lombok 사용법: @Getter @NoArgsConstructor @AllArgsConstructor @Builder 등 어노테이션에 대해서 익힐 수 있었다.

## 느낌 Feeling
- Lombok 어노테이션 이해를 위해서 프로젝트를 따로 만들어서 실제 빌드된 클래스가 어떻게 만들어지는지 살펴보니 더 깊이 이해할 수 있었다.

## 교훈 Finding
- johngrib님이 어노테이션 등을 애매하게 알고 쓰기보다는 공식 문서를 찾아보고 설명하는 글을 작성하기를 권했다. 
- 다음 주에는 애매하게 알고 있는 것들을 정리해봐야겠다. 예를 들면 테스트 커버리지 작동법 등.

## 피드백 Feedback
### [코드 리뷰](https://github.com/CodeSoom/spring-week5-assignment-1/pull/58) - by johngrib님
- ENH, TST라는 프리픽스를 사용하셨는데요. 지금 이 프로젝트는 혼자 작업하는 프로젝트가 아닙니다. 제가 동료로 함께 일하고 있는 프로젝트라고 생각하세요. 그렇다면 이런 프리픽스를 쓰려면 어떤 의미를 갖고 있는지 설명해주고, 동의를 얻은 다음에 사용하는 것이 좋겠죠.
- @NoArgsConstructor @AllArgsConstructor 이 두 롬복 애노테이션은 매우 주의깊게 사용해야 합니다. 사용을 금지하는 회사들도 많습니다. 그 이유에 대해 조사해 보세요.
- @Builder를 클래스 시그니처 위에 선언하지 않고 각 생성자 위에 선언하도록 합시다. 이렇게 할 때 어떤 점이 다른지에 대해서도 조사해 보세요
- 예외 메시지를 받는 생성자도 추가해 보세요. 활용해 보는 연습을 해봅시다.
- UserData의 핵심 메소드를 뽑아 UserCreateRequest라는 이름의 인터페이스를 만들어 볼 수 있겠죠. 그러면 이 메소드는 인터페이스를 입력 파라미터로 선언해서 UserData 클래스가 여기까지 침투하는 것을 막을 수 있을 겁니다
- @GeneratedValue가 어떤 전략들을 취할 수 있는지 조사해 보세요.
- @Primary가 bean 주입에 대해 어떤 역할을 하는지 설명해 보세요. 
- "알고 있습니다"라는 표현이 아쉽습니다. Spring 공식 문서에서 @Primary를 찾아 보시고, 설명하는 글을 작성해 보세요. 귀찮으실 수도 있겠지만 애매하게 아는 것들을 공식 문서를 보면서 확보해 나갈 수 있다면 몇 년 후에 많이 성장해 있으실 거에요.
- UserServiceTest에서 mock의 역할이 필요 이상으로 커 보입니다. 결과를 맞춰놓고 테스트하고 있어서 UserRepository 구현의 변경에 테스트코드가 따라가지 못할 위험이 있습니다. mock과 given을 제거하고 테스트 코드를 작성해 보는 걸 권해드리고 싶습니다. 
