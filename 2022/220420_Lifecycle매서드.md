# LifeCycle 메서드

9개가 존재하는데 크게 생성(마운트), 업데이트, 제거(언마운트)의 세가지 유형으로 나눌 수 있습니다.

**마운트**는 컴포넌트의 인스턴스가 생성되어 DOM 상에 삽입될 때 일어납니다.

**업데이트**는 props 또는 state가 변경되고 컴포넌트가 재렌더링될 때 발생합니다.

**언마운트**는 DOM에서 제거될 때 일어납니다.

클래스형에서 사용 가능하며, 함수형 같은 경우 리액트 훅으로 해당 기능들을 수행할 수 있습니다.
