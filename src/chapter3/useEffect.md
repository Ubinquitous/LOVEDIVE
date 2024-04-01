## useEffect

부수 효과를 만드는 함수.

## 주의할 점

- 잘못 사용하면 예기치 못한 버그가 발생할 수 있음
- 심각한 경우 무한 루프가 걸림 (이 덕분에 AWS 150만원 날림)

## eslint-disable-line react-hooks/exhaustive-deps 주석 지양

이 주석은 지양해야 한다. 정말로 필요할 땐 사용할 수 있지만,  
의존성에 빈 배열을 넣는 코드는 버그를 만들 가능성이 매우 크기 때문.

## useEffect에 함수명 부여하기

```jsx
useEffect(function fetchData() {
    fetch( ... )
}, [...])
```

## 거대한 useEffect 만들지 말기

- useEffect가 커지면 어디서 오류가 발생하는지 모름.
- 의존성을 여러개로 쪼개서 차라리 작은 useEffect 여러개를 만들자

## 불필요한 외부 함수 만들지 말기

- 불필요한 코드가 많아지고 가독성이 떨어짐
- 내부로 가져오면 훨씬 코드가 간결해짐.
