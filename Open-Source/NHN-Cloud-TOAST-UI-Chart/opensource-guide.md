## Open Source > NHN Cloud UI Chart > 오픈 소스 사용 가이드

## 설치하기

NHN Cloud TOAST UI 제품들은 패키지 매니저를 이용하거나, 직접 소스 코드를 다운받아 사용할 수 있다. 하지만 패키지 매니저 사용을 권장한다.

### 패키지 매니저 사용하기

NHN Cloud TOAST UI 제품들은 [npm](https://www.npmjs.com/) 패키지 매니저에 등록되어 있다.
각 패키지 매니저가 제공하는 CLI 도구를 사용하면 쉽게 패키지를 설치할 수 있다. npm 사용을 위해선 [Node.js](https://nodejs.org)를 미리 설치해야 한다.

#### npm
```sh
$ npm install --save @toast-ui/chart # 최신 버전
$ npm install --save @toast-ui/chart@<version> # 특정 버전
```

### Contents Delivery Network (CDN) 사용하기

NHN Cloud TOAST UI Chart는 CDN을 통해 사용할 수 있다.

- 아래의 코드로 CDN을 사용할 수 있다.

```html
<link rel="stylesheet" href="https://uicdn.toast.com/chart/latest/toastui-chart.min.css" />
<script src="https://uicdn.toast.com/chart/latest/toastui-chart.min.js"></script>
```

- CDN은 아래의 디렉토리 구조로 구성되어 있다.

```
- uicdn.toast.com/
  ├─ chart/
  │  ├─ latest
  │  │  ├─ toastui-chart.js
  │  │  ├─ toastui-chart.min.js
  │  │  ├─ toastui-chart.css
  │  │  ├─ toastui-chart.min.css
  │  ├─ v4.0.0/
```

### 소스 파일 다운로드

- [각 버전의 소스코드 다운로드 하기](https://github.com/nhn/tui.chart/releases)

## 사용하기

### HTML

NHN Cloud TOAST UI Chart가 생성될 컨테이너 요소를 추가한다.

```html
<div id="chart"></div>
```

### 자바스크립트

#### 불러오기

NHN Cloud TOAST UI 차트는 생성자 함수를 통해 인스턴스를 생성할 수 있다. 생성자 함수에 접근하기 위해서는 환경에 따라 접근할 수 있는 세 가지 방법이 존재한다.

```js
/* namespace */
const Chart = toastui.Chart;
```
```js
/* Node.js의 CommonJS */
const Chart = require('@toast-ui/chart');
```
```js
/* Node.js의 ES6 */
import Chart from '@toast-ui/chart';
import { BarChart } from '@toast-ui/chart';
```

[Webpack 4 에서는 패키지 모듈을 가져올 때 main 필드보다 module 필드에 정의된 진입점을 우선적으로 가져온다](https://webpack.js.org/configuration/resolve/#resolvemainfields). 만약 프로젝트에서 Webpack 4를 사용하고 `require` 구문을 사용해 `@toast-ui/chart`를 불러온다면, module 필드에 정의된 ESM 파일이 로드될 것이며, require 구문으로 가져올 수 있도록 트랜스 파일 될 것이다. 프로젝트에서 **UMD 용 번들 파일이 필요**하다면 `@toast-ui/chart/dist/toastui-chart.js` 혹은 `@toast-ui/chart/dist/toastui-chart.min.js` 파일을 직접 로드하여 사용해야 한다.

```js
const Chart = require('@toast-ui/chart/dist/toastui-chart.min.js'); // // UMD 용 번들 파일 로드
```

Webpack 5는 **exports** 필드를 지원한다. 패키지에서 정의된 **exports** 필드를 보고 모듈 진입점을 판단할 수 있다. 또한 아래와 같이 서브 경로로 접근하여 필요한 차트 파일을 로드할 수 있다.

```js
const Chart = require('@toast-ui/chart'); // ./dist/toastui-chart.js

import { BarChart } from '@toast-ui/chart'; // ./dist/esm/index.js

import BarChart from '@toast-ui/chart/bar';
import ColumnChart from '@toast-ui/chart/column';
import LineChart from '@toast-ui/chart/line';
import AreaChart from '@toast-ui/chart/area';
import LineAreaChart from '@toast-ui/chart/lineArea';
import ColumnLineChart from '@toast-ui/chart/columnLine';
import BulletChart from '@toast-ui/chart/bullet';
import BoxPlotChart from '@toast-ui/chart/boxPlot';
import TreemapChart from '@toast-ui/chart/treemap';
import HeatmapChart from '@toast-ui/chart/heatmap';
import ScatterChart from '@toast-ui/chart/scatter';
import LineScatterChart from '@toast-ui/chart/lineScatter';
import BubbleChart from '@toast-ui/chart/bubble';
import PieChart from '@toast-ui/chart/pie';
import NestedPieChart from '@toast-ui/chart/nestedPie';
import RadarChart from '@toast-ui/chart/radar';
```

### CSS

Chart를 사용하기 위해서는 CSS 파일을 추가해줘야 한다. import, require를 통해 CSS 파일을 불러오거나, CDN을 통해 불러올 수 있다.

* ES6 모듈

```js
import '@toast-ui/chart/dist/toastui-chart.min.css'; // Chart 스타일
```

* Common JS

```js
require('@toast-ui/chart/dist/toastui-chart.min.css');
```

* CDN

```html
<link rel="stylesheet" href="https://uicdn.toast.com/chart/latest/toastui-chart.min.css" />
```


### 인스턴스 만들기

생성자 함수는 **el**, **data**, **options** 세 개를 인자로 갖는다.

- el: 차트를 자식요소로 갖는 HTML 요소
- data: 차트의 기반이 되는 숫자 데이터
- options: 범례, 정렬, 툴팁 포맷 등 여러 기능을 나타내는 옵션

```js
const el = document.getElementById('chart');
const data = {
  categories: ['Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
  series: [
    {
      name: 'Budget',
      data: [5000, 3000, 5000, 7000, 6000, 4000, 1000],
    },
    {
      name: 'Income',
      data: [8000, 4000, 7000, 2000, 6000, 3000, 5000],
    },
  ],
};
const options = {
  chart: { width: 700, height: 400 },
};

const chart = Chart.barChart({ el, data, options });
// const chart = new BarChart({ el, data, options }); // 두 번째 방법
```
![image](https://user-images.githubusercontent.com/35371660/105698632-79769d00-5f49-11eb-8ae5-0d0f648f9ac6.png)
