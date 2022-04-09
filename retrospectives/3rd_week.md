# 2주차 회고  
기간: 2022. 4. 3.  ~ 4. 9.

## 사실 Fact
### 알게 된 것
- [JUnit5](https://junit.org/junit5/docs/current/user-guide/): Java 단위 테스트 라이브러리
- [AssertJ](https://joel-costigliola.github.io/assertj/): 좀 더 이해하기 쉽게 단정문을 쓸 수 있는 자바 라이브러리
```Java
# JUnit5
assertEquals(task.getTitle(), "Title");

# AssertJ
assertThat(task.getTitle()).isEqualTo("Title");
```
hasSize가 더 읽었을 때 이해하기 쉽다
- [MockMVC](https://spring.io/guides/gs/testing-web/): 실제 서버에 요청해서 테스트하지 않고 가짜로 요청과 응답을 만들어 쉽게 테스트할 수 있도록 도와줌
- [Mockito](https://site.mockito.org/): 가짜 객체를 쉽게 만들 수 있게 도와주는 프레임워크

### 익힌 것
- JUnit5와 AssertJ를 활용한 단위 테스트. AssertJ를 써보니 JUnit5만 쓰는 것보다 확실히 이해하기 쉬웠다. 
- MockMVC를 활용한 테스트 기법
- SpringBootTest, Autowired

## 느낌 Feeling
- Mock 사용법이 아직 익숙하지 않았다. Mock 사용법을 더 찾아보고 연습해야할 거 같다.
- 모델의 경우 굳이 테스트가 필요한가 의문이다.

## 교훈 Finding
- 테스트 대상이 2개이면, 분리하기!

## 피드백 Feedback
### [코드 리뷰](https://github.com/CodeSoom/spring-week3-assignment-1/pull/65)
- "할 일을 생성하고 제대로 등록되었는지 확인하는 테스트와, 존재하지 않는 할 일을 조회했을 때 예외를 던진다는 것 2가지를 테스트하고 계신 것 같아요. 테스트 대상이 2개이면, 이 테스트가 깨질 수 있는 가능성이 2개가 되고 이 것은 유지보수를 어렵게 합니다. 따라서 테스트를 분리하는게 좋을 것 같아요" - 윤석님
- "코드가 한 줄로 모두 이어져 있어서 구분하기 어려운 것 같아요. 우리가 글을 작성할 때도 적절하게 문단을 나누면 읽기 좋잖아요? 코드를 작성할 때도 마찬가지입니다. 관련이 있는 것들끼리 적절히 묶고, 빈 줄을 활용해서 구분해주면 좋을 것 같아요." - 윤석님
- "한 줄로 되어있어서 조금 읽기가 어려운 것 같네요. 적절히 줄바꿈을 해주는 것은 어떨까요?" - 윤석님
- "Task 객체에 대해서 아주 꼼꼼하게 테스트를 작성해 주셨네요! 테스트를 우리가 작성한 코드의 예제라고 생각해 봅시다. 테스트가 꼼꼼하게 작성되어 있다면 하나하나의 기능에 대해서는 좋겠지만, 전체적으로 어떻게 사용하는지는 판단하기 어려울 수도 있을 것 같아요. 따라서 이 객체를 어떻게 사용하는지를 간단하게만 작성해 보는 것도 좋을 것 같아요" - 윤석님
