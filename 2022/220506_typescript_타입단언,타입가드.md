<!-- 220506_typescript_타입단언,타입가드.md -->
# 타입스크립트 타입단언, 타입가드
## 타입 단언(type assertion)
개발자가 정의한 대로 타입 지정
```typescript
var a;
a = 20;
a = 'a';

// a가 처음에 타입 any를 가지고 있고, 중간에 바뀌었으나 반영 X
// 개발자가 확인했을 때는 딱 string이 되었다는 것을 알 수 있음

// as string으로 입력해주면 b에 string값이 할당됨
var b = a as string;
```

## 타입 가드(type guard)
### 기본 코드
```typescript
interface Developer {
    name: string;
    skill: string;
}

interface Person {
    name: string;
    age: number;
}

// 유니온 타입은 공통된 속성만 접근할 수 있음 - 직접 명시해줘도 안됨
function introduce(): Developer | Person {
    return { name: 'Tony', age: 33, skill: 'Iron Making' }
}
var tony = introduce();
// console.log(tony.skill);
```

### 타입 단언만 사용했을 때의 문제점
- 코드 계속해서 반복
```typescript
if ((tony as Developer).skill) {
    var skill = console.log(((tony as Developer).skill));
    console.log(skill);
} else if ((tony as Person).age) {
    var age = console.log(((tony as Person).age));
    console.log(age);
}

```

### 타입 가드
타입가드 함수 is타입변수
```typescript
function isDeveloper(target: Developer | Person): target is Developer {
    return (target as Developer).skill !== undefined;
}

if (isDeveloper(tony)) {
    console.log(tony.skill)
} else {
    console.log(tony.age)
}
```