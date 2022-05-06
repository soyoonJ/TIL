# 타입스크립트 타입추론
## 타입 추론 기본
```typescript
// 값을 할당하면 변수 타입이 추론됨
var a = 10;

// 파라미터에 b가 없으면 10이 할당 => 10 할당될 경우 b가 number라고 추론
function getB(b = 10) {
    var c = 'hi'
    return b+c;
}

10 + '10' // 1010
```

## 타입 추론 기본 2
### 인터페이스 & 제네릭
```typescript
interface Dropdown<T> {
    value: T;
    title: string;
}
var shoppingItem: Dropdown<string> = {
    value: 'abc',
    title: 'hello'
}
```

## 타입 추론 기본 3
### 제네릭 연달아 두 개 나왔을 경우
```typescript
interface Dropdown<T> {
    value: T;
    title: string;
}
interface DetailedDropdown<K> extends Dropdown<K> {
    description: string;
    tag: K;
}

var detailedItem: DetailedDropdown<string> = {
    title: 'hello',
    description: 'ab',
    value: 'a',
    tag: 'a',
}
```

## Best Common Type
```typescript
var arr = [1, 2, true, true, 'a'];
```