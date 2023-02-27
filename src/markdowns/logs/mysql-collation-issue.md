---
question: 'mySQL collation은 어떻게 처리하는 것이 맞나?'
slug: '23-02-27-01'
---

### 문제

bénédictine이라는 재료를 사용할 때 WHERE 절에서 latin1_swedish_ci가 utf8_general_ci와 맞지 않다는 에러가 발생하였다. GCP VM 인스턴스에서 ubuntu 18.04에서 발생한 에러이다. 기존에 맥에서 동일한 로직을 실행했을 때에는 에러가 발생하지 않았다. mysql> status를 확인했을 때 ubuntu는 latin1으로 되어있었고, mac은utf8mb4로 되어있었다. 테스트환경에서 발생하면 문제가 없는데 프로덕션에서 위와 같은 이슈가 발생하면 어떻게 하지? 갑자기 mysql 서버의 collation을 모두 utf8mb4로 바꾸어버리면 잠재적 에러가 있지 않을까?
