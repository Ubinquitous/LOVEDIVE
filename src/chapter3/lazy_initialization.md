## 게으른 초기화

- 게으른 초기화는 useState()의 인수로 함수를 넣어주는 경우이다.
- state가 처음 만들어질 때만 사용되고 리렌더링이 발생하면 함수 실행은 무시된다.
- localStorage나 sessionStorage, map, filter, find 등을 사용하는 등의 실행 비용이 많이 드는 경우 사용하는 것이 좋다.
