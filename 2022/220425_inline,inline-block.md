# inline과 inline block의 차이점

### block

_: 제목, 시멘틱 태그, 테이블 관련, 목록 태그, 레이아웃 관련 태그_

• inline과 달리, 새로운 줄로 시작하며 해당 줄의 가로를 다 차지한다.

• block을 default값으로 가지고 있는 tag: `<div>, <h1>, <p>, <li>, <section>`

---

### inline

_: 글자 꾸미는 서식 관련된 부분이 많음_

- 태그 안의 글자 길이만큼의 영역만 화면에 표시한다.
- inline을 default값으로 가지고 있는 tag: `<span>, <a>, <img>, <em>, <i>, <strong>,`
- line-height 적용 가능
- `width, height` 속성에 영향을 받지 않는다
- 상하 마진을 가질 수 없음

### inline-block

- inline과 같이 양 옆으로 화면에 나열할 수 있다.
- line-height 적용 가능
- inline-block을 default값으로 가지고 있는 tag: `<button>, <input>, <select>, <textarea>`
- `width, height` 속성을 통해 사이즈 조절이 가능하다.
- margin/padding → top/bottom 적용 가능
