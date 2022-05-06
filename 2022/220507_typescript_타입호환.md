<!-- 220507_typescript_타입호환.md -->
# 타입스크립트 타입호환
## 인터페이스, 클래스
```typescript
interface Developer {
    name: string;
}
interface Person {
    name: string;
    skill: string;
}
// class Person {
//     name: string;
// }

var developer: Developer;
var person: Person;
// var person = {name: "Captain", location: "Pangyo"}
// 타입호환 - 오른쪽에 있는 속성이 왼쪽에 있는 속성보다 더 클 때 호환 가능
// developer가 person보다 많은 속성을 가지고 있으면 developer에서 오류 발생
developer = person;
// developer = new Person();
// person = developer;
```

## 함수
```typescript
// sum 함수가 add 함수보다 더 큼
var add = function(a: number) {
    // console.log()
}
var sum = function(a: number, b: number) {
    // return a+b
}
sum = add;
// add는 하나의 파라미터만 받을 수 있기 때문에 넣는 것이 불가능
// add = sum;
```

## 제네릭
```typescript
interface Empty<T> {
    // ..
}
var empty1: Empty<string>;
var empty2: Empty<number>;
empty1 = empty2;
empty2 = empty1;

interface NotEmpty<T> {
    data: T;
}
var notempty1: NotEmpty<string>;
var notempty2: NotEmpty<number>;
// 제네릭 타입 인자가 속성에 할당되면 서로 다른 타입으로 간주되어 오류 남
// notempty1 = notempty2;
// notempty2 = notempty1;
```