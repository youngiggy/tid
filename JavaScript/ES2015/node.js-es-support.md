#node.js의 ES2015 지원 상황
[ECMAScript 6 compatibility table](https://kangax.github.io/compat-table/es6/)
- module은 아직 V8 엔진에 반영이 안 됐다.
  - 그래서 import를 쓸 수 없다.
    - require를 쓰거나 babel을 쓰거나!
    
- babel을 쓰려면 preset을 쓰는 게 좋겠다
  - (https://blog.outsider.ne.kr/1176)
  - grunt/gulp같은 task manager를 사용해도 되고
  - package.json에 stat script를 정의하고, 그 안에서 babel 모듈을 require해서 써도 된다.
    - [예시](https://github.com/ediket/graphql-relay-rethinkdb-example)



