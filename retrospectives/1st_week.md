# 1주차 회고  
기간: 2022. 3. 20.  ~ 3. 26.

## 사실 Fact
- [Gradle](https://gradle.org/): Gradle을 사용해서 프로젝트 생성
```ssh
$ brew install gradle
$ gradle init
```
- [Jackson](https://github.com/FasterXML/jackson): GSON만 주로 쓰다가 이번에 사용했다.
- HttpServer 클래스로 자바 서버 구현
관련 코드 중 일부
```ssh
public class App {
    public static void main(String[] args) {
        int PORT = 8000;
        try {
            InetSocketAddress address = new InetSocketAddress(PORT);
            HttpServer httpServer = HttpServer.create(address, 0);
            HttpHandler handler = new AppHandler();
            httpServer.createContext("/", handler);
            httpServer.start();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
- [HTTT 완벽 가이드](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=49731592) 책: 웹 개발자라면 계속 살펴볼 책. 구매 완료!
- 애자일 회고 기록 방식 [3Fs(Fact, Feeling, Finding) + Future Action, Feedback](http://egloos.zum.com/agile/v/4122099)

### 기억에 남는 단어나 문장
- 다른 사람의 좋은 점, 아이디어를 내것으로 만드는 '훔치기'!, 3월 20일 오리엔테이션에서

## 느낌 Feeling
- 출퇴근 시간에 코드숨 강의를 듣고, 퇴근 뒤에 코드 작성을 하려니 쉽지 않았다.
- 목표 수정해야겠다. 과정을 열심히 해내는 것이 아니라, 완주하는 것으로. 
- 회고가 익숙하지 않다. 

## 교훈 Finding
- 구현 우선 습관: 기존 습관대로 구현 우선으로 개발했다. 시간이 없다는 생각에 테스트 코드는 생각을 못하고 구현부터 했다. 테스트 코드는 맨 마지막에 Serializer만 추가했다. 

### 아이디어 Idea
- jest로 python API서버 테스트하기: 과제의 테스트 코드를 보고 Python으로 API 서버를 개발할 때, pytest로 엔드포인트별 테스트를 진행했다. 꼭 pytest가 아니라 Node.js를 활용해서 jest로 해도 되겠다는 생각이 들었다.

## 미래 계획 Future Action
- 테스트 코드 작성과 구현을 동시에 진행하기!
- 회고 목적, 방식 등에 대해서 더 조사하기.

## 피드백 Feedback
### [코드 리뷰](https://github.com/CodeSoom/spring-week1-assignment-1/pull/76)
- "static은 최소한으로 쓰는 게 좋습니다." - 아샬님
- ""localhost"라는 이름을 보니 도메인 주소 혹은 IP주소를 입력받는 곳 인것 같네요. 단순한 숫자는 우리가 무엇을 나타내는지 이해하기 어려워요. 왜 0이어야 하지? 왜 8001은 안되지? 를 파악할 수가 없기 때문이에요. 따라서 상수로 추출해보시면 좋을 것 같아요." - 윤석님
- 한꺼번에 코드를 PR해서 아래와 같은 피드백을 받았다.
```
음 저는 좀 당황스럽네요. 거의 첫 번째 리뷰인데, 과정을 전혀 모르는 복잡한 코드를 한 번에 리뷰해야해서 어렵게 느껴져요.
코드숨 교육과정과 과제의 의도는 처음부터 큰 설계를 하지 않고, 최대한 빠르게 작동하는 소프트웨어를 만들고 리팩터링하는 걸 훈련하는 거에요.
“지금 내 능력으로는 해결하기 어려운 문제를 만났을 때 제일 먼저 무엇을 할 것인가?”를 훈련하는 거죠. 이미 알고 있는 걸 장황하게 억지로 끼워맞추는 건 장기적으로 독이 될 수 있어요. 만약 하루 밖에 시간이 없다면? 만약 한 시간 밖에 시간이 없다면? 만약 십 분 밖에 시간이 없다면? 만약 지금 당장 긴급 패치를 해야 한다면? 이런 식으로 다양하게 시간을 바꿔가면서 고민하면 경우의 수가 늘어나서 선택지를 늘리는 훈련을 할 수 있게 되죠." - 윤석님
```
- "UPPER_SNAKE_CASE는 static final에만 사용하는 관례가 있습니다." - 윤석님
