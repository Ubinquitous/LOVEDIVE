## 서버사이드렌더링

기술은 계속 발전하지만 웹사이트의 성능은 5년 전과 똑같이 느려 역효과가 나는 문제가 발생해서  
최근에 다시 대두된 렌더링 기법.

## 장점

- 최초 페이지 진입이 비교적 빠르다
- SEO, 메타데이터 제공이 쉽다
- Layout Shift가 적다
- 사용자의 디바이스 성능에 비교적 자유롭다 (브라우저 번들링에 모든 것을 맡기지 않기 때문)
- 보안에 좀 더 안전하다

## 단점

- 소스 코드를 작성할 때 서버를 고려해야 한다
- 적절한 서버가 구축돼야 한다
- 서비스 지연

## 서버사이드렌더링은 만능이 아니다

성능에 있어서 만병통치약이 아니기 때문에 SPA, SSR 모두 알아야 함.

## Gmail

- 이미지 등의 리소스는 lazy loading, 코드 스플리팅을 통해 불필요한 리소스 다운&실행 방지
- 대표적인 완전 짱짱인 SPA
