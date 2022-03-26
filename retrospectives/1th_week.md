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

## 발견 Finding
- 구현 우선 습관: 기존 습관대로 구현 우선으로 개발했다. 시간이 없다는 생각에 테스트 코드는 생각을 못하고 구현부터 했다. 테스트 코드는 맨 마지막에 Serializer만 추가했다. 

### 아이디어 Idea
- jest로 python API서버 테스트하기: 과제의 테스트 코드를 보고 Python으로 API 서버를 개발할 때, pytest로 엔드포인트별 테스트를 진행했다. 꼭 pytest가 아니라 Node.js를 활용해서 jest로 해도 되겠다는 생각이 들었다.

## 미래 계획 Future Action
- 테스트 코드 작성과 구현을 동시에 진행하기!
- 회고 목적, 방식 등에 대해서 더 조사하기.

## 피드백 Feedback
