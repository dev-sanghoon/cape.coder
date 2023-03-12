---
question: '패키지 결정 기준은 어떻게 해야 하나?'
slug: '23-03-12-01'
---

### 문제

서버에서 활용할 로깅 패키지를 찾는데, 무슨 기준으로 로깅 패키지를 선택해야 하나 고민이 된다.

[로깅의 장점](https://levelup.gitconnected.com/better-logs-for-expressjs-using-winston-and-morgan-with-typescript-1c31c1ab9342)에서 설명하는 로그의 장점이 납득이 되었다.

- 타임스탬프: 구현하기 매우 귀찮은 부분이다... 간단한 API를 제공하여 보기 쉽게 제공해준다면 너무 좋을 듯
- 로그 파일 저장 기능: fs 쓰면 간단하게 저장 할 수 있긴 한데... 수많은 사람들이 쓰면서 개량된 기능들을 쓰는 것은 가치가 있지. 다만 로그 파일이 쌓였을 때 삭제할 방법도 생각해두긴 해야 한다... 로그 파일 용량이 별로 크지 않나? 수많은 요청/응답이 있다면 유지보수하기가 무척 힘들 듯 한데...
- 로그 레벨에 따라 표시 변경: 개별 로그에 레벨을 지정할 수 있고, env에 따라서 표시 여부, 색 등을 변경할 수 있는 기능. 있으면 좋은데, 이건 그렇게 중요한지는 잘 와닿진 않는다.

더 알아보다가, [console.log는 JS의 성능에 악영향을 미친다](https://yceffort.kr/2021/02/logging-in-nodejs)는 놀라운 내용을 접했다.

그냥 winston + morgan (가장 대중적인 픽인듯 하다)를 쓰려다 구글에서 nodejs loggers compared를 찾아 [좋은 글](https://geshan.com.np/blog/2021/01/nodejs-logging-library/)을 찾았다.

winston은 [Motivation에서 transport를 강조](https://github.com/winstonjs/winston#motivation)하고 있다. transport는 로그가 저장되는 위치를 의미한다. 저장 위치를 다양하게 할 수 있다는 것이 장점이다.

bunyan은 로그를 JSON으로 저장한다는 점이 핵심인 듯 하다. ["Server logs should be structured"](https://github.com/trentm/node-bunyan)라고 한다. 로그를 집계하여 데이터화하기엔 좋을 듯 하다. 로그를 프로그램을 사용해서 값을 찾거나 하기에도 좋을 듯 하다.

[pino](https://github.com/pinojs/pino)는 비동기를 강조한다. 만약 로그 때문에 프로그램이 터지는 상황이 생긴다면 (물론 극단적이지만), 그건 로그 자체의 의도와는 다르게 작동하는 것이니까...

[loglevel](https://github.com/pimterry/loglevel)은 쓰기 편한 것이 가장 큰 장점인 듯 하다. 그러나 transport를 제공하지 않는 것을 보니, 어디엔가 로그를 저장하는 기능은 없는 듯 하다. 그러면 좀 아쉽지 않나?....

loglevel이 가장 마음에 드는데, 저장 기능을 제공하지 않는 것 보니 제외하는 것이 맞을 듯 하다. 우선 pino를 사용하고, 향후에 사이드 프로젝트에서 loglevel을 사용해보는 것도 괜찮겠다.

사실 중요한 건 빠르게 로깅 시스템을 구축하는 것이니까, 인터넷에 많은 winston의 best practice를 사용해서 구현하는 것이 우선시되지 않을까? morgan과 조합해서... 싶은 마음도 들고... 고민이다.

### 참고

좋은 글 감사합니다. 큰 도움이 되었습니다. Thank you for sharing great articles!
[Better logs for ExpressJS using Winston and Morgan with Typescript (by
Andrea Vassallo)](https://levelup.gitconnected.com/better-logs-for-expressjs-using-winston-and-morgan-with-typescript-1c31c1ab9342)  
[Nodejs에서 로깅하기 (yceffort 님)](https://yceffort.kr/2021/02/logging-in-nodejs)  
[node.js 서버에서 로그를 남겨보자 (yurlee 님)](https://42place.innovationacademy.kr/archives/9137)
[5 Node.js Logging libraries compared for you to make the optimal choice](https://geshan.com.np/blog/2021/01/nodejs-logging-library/)
