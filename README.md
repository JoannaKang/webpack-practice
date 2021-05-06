0. 웹팩을 사용하는 이유?

- 모듈로 구성된 코드들을 한 파일 (="index_bundle.js")로 묶어서 브라우저에서 그 파일만 로딩하도록 설정
- 장점: 분산된 여러 파일을 로딩하는것보다 속도가 빠르다

1. 웹팩의 구성

- entry : 모듈들이 연결된 번들링이 시작점이 되는 파일
- output: 번들링된 파일이 내보내지는 경로

* 참고: https://webpack.js.org/configuration/entry-context/

2. 웹팩 사용방법

- cli에서 npx webpack --config webpack.config.js 실행 => 번들링된 파일이 만들어진다
- developemnt, production -> 개발모드, 배포용 번들링 파일을 따로 생성할 수도 있음

* 참고: https://webpack.js.org/configuration/mode/#root

3. loader

- 웹페이지 로드에 필요한 자원들(css, font, image...)을 변환할 수 있도록 세팅된 속성들
- module 이라는 이름의 오브젝트 안에 rules를 어레이 형태로 세팅한다
- 특정 확장자를 가진 파일들은 지정된 웹팩 로더들을 활용할 수 있도록 config 파일안에 세팅해두는것
- 로더는 선언된 역순으로 체이닝되어 실행됨

* 참고: https://webpack.js.org/guides/asset-management/

4. output

- 여러개의 entry 파일을 번들링해 output 디렉토리에 내보낼수도 있다
- entry에 오브젝트 형태로 엔트리 파일 이름, 경로를 지정해준다
- output filename 지정 시 [name] 키워드를 이용해 지정하면 entry 오브젝트 안의 키값으로 번들파일 이름이 생성된다.

* 참고: https://webpack.js.org/concepts/output/#root

5. 유용한 플러그인

- HTMLWebpackPlugin: https://webpack.js.org/plugins/html-webpack-plugin/

6. watchmode 실행법

```
wpx webpack --watch
```

7. etc

- DevServer: 개발할 때 사용하는 웹서버, live reload, hot module replacement 기능을 제공 -> 코드 수정 내역을 바로바로 반영해서 확인 가능
- Code spliting: 너무 큰 번들링 파일을 만들지 않기 위해 코드를 쪼개는 것
- Lazy loading: 쪼개진 번들링 파일을 필요할때마다 로딩하는 것
