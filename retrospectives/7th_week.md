# 7주차 회고  
기간: 2022. 5. 1.  ~ 5. 7.

## 사실 Fact
- [Spring Security](https://spring.io/guides/topicals/spring-security-architecture) 활용 방법
- [Bcrypt Java](https://en.wikipedia.org/wiki/Bcrypt) 사용법

## 느낌 Feeling 
- 이번 주 과제와 관계 없는 코드에 1L로 값이 고정된 코드가 있었다. 테스트 코드도 userId를 1L로만 한 바람에 오류를 찾는데 한참 걸렸다.
```java
public String encode(Long userId) {
        return Jwts.builder()
                .claim("userId", 1L)
                .signWith(key)
                .compact();
    }
```

## 교훈 Finding
- 테스트를 한 가지 경우만 하지 않고 경계값 분석 테스트 등 여러가지 경우를 해야겠다.

## 피드백 Feedback
### 코드 리뷰 by johngrib님
[PR #47](https://github.com/CodeSoom/spring-week7-assignment-1/pull/47)
- 이제 올라오는 PR이 많이 줄어서 PR 기준으로 작업하는 방식으로 전환하기 좋을 것 같습니다. 계동님만 괜찮다면 이 PR은 CodeSoom:geydong에 머지하고 다음 작업부터는 작업 주제별로 별도의 PR로 올려볼까요? 회사에서 하는 거랑 비슷하게 해보는 겁니다. PR -> 코드리뷰 -> approve -> merge -> PR 사이클을 돌려보는 거죠.
- 이런 식으로 하면 method가 혹시 null이라 하더라도 문제없죠.
```java
if ("GET".equals(method)) {
```

[PR #61](https://github.com/CodeSoom/spring-week7-assignment-1/pull/61)
- 너무 작은 단위로 수정하는 커밋이 많아서, 리뷰어가 커밋 목록만 보고 작업의 전체 흐름을 파악하기 어렵습니다. 아주 작은 커밋들을 모아서 하나로 합치는 방법 등을 고려해 보세요. 커밋 메시지를 작업의 흐름에 따라 로그를 남기듯 작업하는 것보다 커밋 목록이 작업을 요약해 보여줄 수 있도록 미리 커밋 메시지를 작성해 보는 연습을 해보는 것도 좋습니다. Pr을 여러개로 나눠보는 것도 좋겠죠. 한편 이 PR은 일요일 오후 9시 이후에 올라왔으니 7주차가 종료된 이후에 올라왔다고 할 수 있어요. 새로운 PR은 8주차 리포지토리로 올려주시면 되겠습니다.
