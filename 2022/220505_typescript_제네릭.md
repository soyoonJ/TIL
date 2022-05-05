# typescript 제네릭
단지 타입을 다르게 하기 위해서 중복된 코드를 반복하는 것은 비효율적
```typescript
function logText(text: string) {
    console.log(text);
    // text.split().reverse().join('');
    return text;
}

function logNumber(num: number) {
    console.log(num);
    return num;
}
logText('a');
logText(10);
const num = logNumber(10);
logText(true);
```

## 유니온 타입     
split 쓸 경우 number 가능성이 있기 때문에 split이 불가하다고 나오는 문제점 발생
```typescript
function logText(text: string | number) {
    console.log(text);
    return text;
}
logText('a');
logText(10);
```

## 제네릭 사용
### 제네릭 사용했을 때의 장점       
타입을 비워두고서 호출할 시점에 타입을 지정함
중복 코드 삭제 가능
```typescript
function logText<T>(text:T): T {
    console.log(text);
    return text;
}

const str = logText<string>('abc');
// str이 string일 경우이기 때문에 split도 가능
str.split('')
const login = logText<boolean>(true);
```


## 인터페이스에 제네릭을 선언하는 방법
```typescript
// 일반
interface Dropdown {
    value: string;
    selected: boolean;
}
const obj: Dropdown = { value: 'abc', selected: false };

// 제네릭 붙였을 경우
interface Dropdown<T> {
    value: T;
    selected: boolean;
}
const obj: Dropdown<string> = {value: 'abc', selected: false};
```

## 제네릭의 타입제한
```typescript
function logTextLength<T>(text:T[]):T[] {
    console.log(text.length);
    text.forEach(function (text) {
        console.log(text)
    })
    return text;
}
logTextLength<string>(['hi', 'abc']);

// 제네릭 타입 제한 2 - 정의된 타입 이용하기
interface LengthType {
    length: number;
}
function logTextLength<T extends LengthType>(text: T): T {
    text.length;
    return text;
}
// 문자열 수용함 - 기본적으로 length가 속성에 포함되어 있기 때문
logTextLength('a');
// 숫자 수용불가
// logTextLength(10);
logTextLength({length: 10});

// 제네릭 타입 제한 3 - keyof
interface ShoppingItem {
    name: string;
    price: number;
    stock: number;
}
// ShoppingItem에 있는 키들 중에 한가지가 제네릭이 될 것이다.
// getShoppingItemOption에 들어갈 수 있는 인자는 ShoppingItem에서 정의된 키값 중 지정 가능
function getShoppingItemOption<T extends keyof ShoppingItem>(itemOption: T):T {
    return itemOption;
}
// 오류 남
// getShoppingItemOption(10);
// getShoppingItemOption<string>('a');
getShoppingItemOption("name");
```