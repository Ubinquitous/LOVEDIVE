### 가상 DOM과 리액트 파이버

리액트의 가장 큰 특징 : 가상 DOM

### 렌더링 과정

1. 브라우저가 사용자가 요청한 주소로 HTML 파일 다운
2. 렌더링 엔진이 HTML을 파싱해 DOM 트리 구성
3. CSS 파일을 만나면 또 다운로드, 파싱해 CSSOM 트리 구성
4. 눈에 보이는 노드만 방문(display: none 이런거 무시)해서 분석과정 최적화
5. CSSOM과 매칭시켜서 찾고 레이아웃(좌표 설정), 페인팅(유효한 모습 그리기).

### 가상 DOM

- 요소의 위치와 크기를 재계산해야한다면 레이아웃&리페인팅이 반드시 일어나 더 많은 비용이 듦. (그래서 사이트 최적화할때 이미지 크기 정해둠)
- SPA는 사용자에겐 깜빡임없어서 편하지만 DOM 관리는 부담이 커짐.
- 가상 DOM : 메모리에서 계산하고 올려서 렌더링 과정 최소화.
- 무조건 빠른게 아니라 충분히 합리적으로 빠름. 무조건 빠른건 아님.

### 리액트 파이버

- 가상 DOM과 실제 DOM을 비교하여 변경 사항을 수집하고, 차이가 있으면 파이버를 기준으로 렌더링을 요청함.

#### 하는 일

- 작업을 작은 단위로 분할하고 우선순위를 매김
- 작업을 일시중지하고 나중에 다시 시작할 수 있음
- 이전에 했던 작업을 다시 재사용하거나 필요하지 않으면 폐기 가능

- 이런 요청들은 비동기로 일어남. 옛날에는 리액트가 스택 알고리즘이라서 무조건 동기여서 비효율적이었음.
- 리액트 요소는 렌더링때마다 새롭게 생성되지만 파이버는 가급적이면 재사용됨.

#### 파이버 트리

- 리액트에는 두개의 파이버 트리가 있는데, 하나는 지금 띄워주고있는거, 하나는 작업중인 파이버트리(workInProgress)임.
- 리액트 파이버가 작업이 끝나면 그냥 리액트가 포인터만 workInProgress로 변경해줌. <- 더블 버퍼링