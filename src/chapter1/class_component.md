## 클래스형 컴포넌트

- 함수형 컴포넌트는 꽤 오래된 역사가 깊은 선언 방식임. (초기 Hooks가 없던 시절에는 헤더리스 컴포넌트로 많이 이용됨)

## 클래스형 컴포넌트에서 Component와 PureComponent 차이점

- Component를 상속받았을 때 : state가 변경되지 않아도 state에 접근하면 무조건 렌더링
- PureComponent를 상속받았을 때 : state가 변경되지 않으면 접근해도 렌더링 X

> 그럼 PureComponent가 훨씬 좋은가?

-> X. PureComponent는 얕은 비교만 하기 때문에 복잡한 객체에선 비효율적이고 역효과가 날 수 있음.  
-> 적당히 섞어 쓰는게 효율적인 리팩토링 방식.

## render()

- 항상 순수 함수 여야함.
- this.setState를 직접 호출해선 안됨.

## componentDidMount()

- 컴포넌트가 마운트되고 준비되는 즉시 실행.
- 성능 문제가 일어날 수 있음.

## componentDidUpdate()

- state나 props에 변화에 따른 DOM 업데이트 로 많이 쓰임.

## componentWillUnMount()

- eventListener를 삭제하거나 clearInterval, api 호출 취소 등 cancel 작업 가능

## shouldComponentUpdate()

- 리렌더링되는 걸 막을때 씀 반환값은 boolean
- 성능 최적화 상황에서만 고려해야함

## componentDidCatch()

- 자식 컴포넌트에서 에러가 발생했을 때 실행됨.
- 에러바운더리를 적용하는데 많은 도움이 됨.
- 함수형 컴포넌트에서는 에러바운더리를 만들 수가 없음.

## 클래스형 컴포넌트의 한계

- 데이터 흐름 추적 어려움
- 애플리케이션 내부 로직 재사용 어려움
- 기능이 많아지면 컴포넌트 크기가 커짐
- 함수에 비해 클래스가 어려움
- 번들링된 크기도 큼

## 그래서 공부해야 되는가?

- 클래스형 컴포넌트로 만들어진게 너무 많아서 사라질 계획은 없어보임.
- 공부하다보면 한번쯤은 클래스형 컴포넌트를 공부해볼만함.
- 에러처리를 위해서라도 클래스형 컴포넌트에 대한 지식은 어느정도 필요함.
