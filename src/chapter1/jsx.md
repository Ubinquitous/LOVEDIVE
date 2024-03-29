### JSX

```js
return isHeader ? (
  <h1 className="text">{children}</h1>
) : (
  <span className="text">{children}</span>
);
```

```js
return createElement(
  isHeading ? "h1" : "span",
  { className: "text" },
  children
);
```

위와 같이 element만 다르고 요소가 같은 상황에서는 이렇게 코드를 최소화할수 있다.
