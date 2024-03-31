# Typing

자바스크립트 타입과 관련된 규칙을 정의합니다.

### 함수

- 함수의 인자 타입과 리턴 타입은 항상 적습니다.
- 리턴 타입이 추론될 수 있도록 아래와 같이 처리합니다.
  - 기본적으로 함수 선언으로 함수를 정의합니다.
  - 함수 표현식으로 정의해야할 때는 리턴 타입 뿐 아니라, 변수 자체에 타입 명시를 합니다.

```typescript
function foo(a: number): number {
  return a;
}
const foo: (a: number) => number = (a: number) => {
  return a;
};
```
