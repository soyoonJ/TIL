## ✅ **Webpack이란?**

webpack 은 최신 JavaScript 애플리케이션을 위한 정적 모듈 번들러입니다. webpack이 애플리케이션을 처리할 때, 내부적으로는 프로젝트에 필요한 모든 모듈을 매핑하고 하나 이상의 번들을 생성하는 [디펜던시 그래프](https://webpack.kr/concepts/dependency-graph/)를 만듭니다.

\*모듈 번들링 : html 파일에 들어가는 자바스크립트 파일들을 하나의 자바스크립트 파일로 만들어주는 방식

## ✅ **Webpack을 사용해야 하는 이유**

SPA를 사용할 때 하나의 html 페이지에 여러개의 자바스크립트 파일을 포함.

연관되어 있는 자바스크립트 파일들을 하나의 파일로 묶어주어 관리하기 편하다.

컴파일 할 때 여러 모듈들의 파일을 읽어오는 데 시간이 오래 걸리는데, 이를 해결하기 위해 여러 파일을 하나의 파일로 번들링 해준다. 하나의 자바스크립트 파일로 만들어서 웹페이지 성능 최적화를 해준다.

## ✅ **Webpack vs Gulp vs Grunt vs Browserify**

**_“webpack = (Grunt || Gulp) + Browserify”_**

: 웹팩은 1:1로 대체되기 보다는 해당 기능이 포함되어 있고 더 많은 작업을 할 수 있다는 점에서 유리

- 크고 복잡하며 다양한 리소스들이 들어있는 프로젝트에는 webpack을 사용하는 것이 좋습니다.

- Grunt, Gulp는 오로지 리소스들에 대한 툴로 사용 - 사람의 실수나 반복적인 작업을 줄이기 위한 자동화 툴(task runner) / 자바스크립트를 다룰 줄 알면 쉽게 사용할 수 있음
- Gulp - 동시에 여러 작업 처리 가능&Grunt보다 빠름
- Grunt - 일반적으로 한번에 하나의 작업만 처리

- Browserify는 Node.js기반 javascript code를 브라우저 환경에서도 실행 가능하도록 해준다.
- 브라우저에서 결과를 확인하려면 코드를 컴파일 해야 한다. 순수한 모듈 번들러로, 태스크러너 기능이 부족.
- Browserify는 비슷한 도구이지만 속도면에서 webpack이 더 좋습니다.

## ✅ **Webpack5 Concepts**

### [Entry](https://webpack.js.org/concepts/#entry)

- dependency graph를 만들기 위해 필요한 `Input Source`입니다.
- 직/간접적으로 의존성을 가진 모듈들을 이해합니다.
- 여러개의 entry가 존재할 수 있습니다.
- Default value : `./src/index.js`

### [Output](https://webpack.js.org/concepts/#output)

- Webpack이 생성한 bundles의 결과물의 위치를 지정할 수 있습니다.
- Default value : `./dist/main.js`

### [Loaders](https://webpack.js.org/concepts/#loaders)

- Webpack은 오직 Javascript와 Json만 이해할 수 있는 단점이 있습니다.
- Loader는 다른 Type의 파일을 Webpack이 이해하고 처리가능한 모듈로 변환시키는 작업을 담당합니다.

### [Plugins](https://webpack.js.org/concepts/#plugins)

- 로더는 특정 유형의 모듈을 변환하는 데 사용되지만, 플러그인을 활용하여 번들을 최적화하거나, 애셋을 관리하고, 또 환경 변수 주입등과 같은 광범위한 작업을 수행 할 수 있습니다.
- `require()`를 통해 플러그인을 요청하여 사용

### [Mode](https://webpack.js.org/concepts/#mode)

- `mode` 파라미터를 `development`, `production` 또는 `none`으로 설정하면 webpack에 내장된 환경별 최적화를 활성화 할 수 있습니다. 기본값은 `production`

### [Browser Compatibility](https://webpack.js.org/concepts/#browser-compatibility)

• 웹팩은 ES5를 사용하는 모든 브라우저를 지원합니다. 단 IE8의 아래 버젼은 지원하지 않습니다.
