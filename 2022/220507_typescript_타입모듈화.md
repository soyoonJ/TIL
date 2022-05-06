<!-- 220507_typescript_타입모듈화.md -->
# 타입스크립트 타입모듈화
## 1. 타입 모듈화를 위해 export를 붙여준다
```typescript
// types.ts
export interface Todo {
    title: string;
    checked: boolean;
}
```
여러개를 export 할 때는 한 번에 묶어서 export 해주기!
```typescript
export { Contact, PhoneType }
```


## 2. 사용하고자 하는 곳에서 import 해서 사용해준다.
```typescript
// app.ts
import { Todo } from './types'

var item: Todo = {
    title: '할 일 1',
    checked: false,
}
```