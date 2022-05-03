# 연산자를 이용한 타입 정의
## **유니온 타입**
하나의 타입 이상을 쓸 수 있도록 함

```typescript
function logMessage(value: string | number) {
    if(typeof value === 'number') {
        value.toLocaleString();
    }
    if (typeof value === 'string') {
        value.toString();
    }
    throw new TypeError('value must be string or number');
}
logMessage('hello');
logMessage(100);
```

union type이랑 인터섹션 타입 중에서는 union type을 실무에서 더 많이 쓰긴 함

```typescript
function askSomeone(someone: Developer | Person) {
    // name, skill, age를 다 줄 거라고 생각하지만 union type임에도 name만 가능함
    // 따로따로 주고 싶으면 위에처럼 if (typeof someone==='Developer') 이런식으로 써줘야 함
    // someone.name
}
두 타입 중에 하나만 작성해서 넘겨도 됨
askSomeone({name: '디벨로퍼', skill: '웹 개발'});
askSomeone({name: '캡틴', age: 100});
```


## **인터섹션 타입**
```typescript
function askSomeone(someone: Developer & Person) {
    // 인터섹션 타입 & 은 에러 따로 안남
    someone.name;
    someone.skill;
    someone.age;
}
// 둘 중에 하나만 쓰는 게 아니라 셋 다 모두 넘겨야 함
askSomeone({name: '디벨로퍼', skill: '웹 개발', age:34});
```