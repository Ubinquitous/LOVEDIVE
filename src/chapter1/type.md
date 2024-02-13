## 리액트 개발을 위해 꼭 알아야 할 자바스크립트

### 자바스크립트의 원시 타입

> 원시 타입 : 객체 타입이 아닌 모든 타입

boolean, null, undefined, string, number, symbol, bigint

#### bigint

- 기존 number의 한계 개선
- 숫자 뒤에 n 또는 BigInt() 생성자로 호출 가능

#### symbol

- 중복되지 않는 고유한 값을 나타내기 위함

### 객체 타입

- 참조 타입이라고도 부름. 동등 비교할 때 참조 주소가 다르면 false
- ===써도 false나옴

### Object.is

===보다 개발자에게 유쾌한 결과 반환

```js
Object.is(-0, +0); // false
Object.is(Number.NaN, NaN); // true
Object.is(NaN, 0 / 0); // true
```

### 리액트에서 동등비교

리액트 개발팀이 만든 shallowEqual이라는 함수 씀  
얕은 객체까지 동등비교하고 (depth<=1) 나머진 컷  
그래서 depth2인 props는 메모이제이션이안됨
