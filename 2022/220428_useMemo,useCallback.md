# React hooks useMemo와 useCallback에 대해 아는대로 설명해주세요

### **memoization**

기존에 수행한 연산의 결과값을 저장해두고 동일한 입력이 들어왔을 때 재활용하는 프로그래밍 기법

### **useMemo**

메모이제이션된 '**값**'을 반환

```jsx
useMemo(() => fn, deps);
```

```jsx
// ex가 변할 때만 console.log(ex) 실행
useMemo(() => {
  console.log(ex);
}, [ex]);
```

### **useCallback**

메모이제이션된 '**함수**'를 반환

```jsx
useCallback(fn, deps);
```

```jsx
...
const [ex, setEx] = useState(0);
const [why, setWhy] = useState(0);
...
const useCallbackReturn = useCallback(() => {console.log(why)}, [ex]);
```

1. 처음 컴포넌트가 시작될 때 실행 **() => {console.log(0)}**
2. ex 가 변할 때까지 함수는 **() => {console.log(0)}**
3. **ex 가 변한다면** 그제서야 why 의 값을 가져와서 **() => {console.log(새로운 값)}**
