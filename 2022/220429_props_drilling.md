# ✅ props drilling

## **Props drilling이란?**

Props drilling은 props를 하위 컴포넌트로 전달하는 용도로만 컴포넌트를 사용하는 것

오직 전달하는 목적으로만 사용하는 부분이 늘어나게 된다면 코드 추적이 어려워 가독성이 안 좋아지고 유지보수가 어려워진다

## **Props drilling을 피하는 방법**

전역 상태관리 라이브러리 사용

`redux`, `MobX`, `recoil` 등을 사용
