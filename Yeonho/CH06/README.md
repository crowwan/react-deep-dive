# React DevTools

### React DevTools?

리액트 환경에서 개발 된 애플리케이션을 디버깅하기 위해 만들어짐
Web 환경 뿐만 아니라 네이티브 등 다양한 플랫폼에서 사용할 수 있음

웹 환경에서의 설치는 각 브라우져의 확장 도구로 설치하면 됨
React로 개발된 App에서 활성화 됨

### 기능 - Components

App을 구성하는 컴포넌트 트리를 확인할 수 있다.
만약, 가명함수로 되어있는 경우 컴포넌트명이 `Anonymouse` 와 같이 표현된다.
이와 비슷한 상황으로 `Anonymouse`와 같이 표현되는 경우들이 있다.

- 익명 함수를 default로 export한 컴포넌트의 경우에도, 다른 컴포넌트에서 import를 통해 불러 사용하였을 때 똑같이 `Anonymouse` 라 표현된다.

- memo를 사용해 익명함수로 만든 컴포넌트를 감싼 경우, 함수명을 명확히 추론하지 못하여 `Anonymouse`로 표시된다.
  추가적으로 memo 라벨을 통해 memo를 통해 감싸진 컴포넌트임을 알 수 있다.

- 고차 컴포넌트의 경우에도 익명함수로 감싸져있다면 마찬가지로 `Anonymouse`로 표현된다.

컴포넌트 트리에서, props, hooks 등 또한 확인이 가능하다.

마지막으로 컴포넌트를 렌더링한 주체, `rendered by` 를 통해 부모 컴포넌트를 확인(개발모드에서만)할 수 있으며 부가적으로 react-dom 의 버전을 확인할 수 있다.

### 기능 - Profiler

components 기능이 정적인 현재 리액트 컴포넌트 트리의 내용을 확인하기 위한 수단이라면, 프로파일러는 리액트가 렌더링하는 과정에서 발생하는 상황을 확인하기 위한 도구이다.

이를 잘 확인하면, 렌더링 과정에서 퍼포먼스 저하, 예상하지 못한 결과에 대한 추론을 할 수 있다.

- 기본적으로 녹화 시작, 녹화 중단, 프로파일링 종료를 통해 특정 시점에 대한 태스크를 녹화할 수 있다.
- **_Flamegraph -_** 렌더 커밋별로 어떠한 작업이 일어났는지 나타낸다. 너비가 넓을 수록 컴포넌트 렌더링하는 데 오래 걸렸다는 의미이므로, 눈에 보이는 것과는 다르게 다른 이유로 인하여 퍼포먼스 저하가 일어날 수 있음을 알 수도 있다.
- **_Ranked -_** 해당 커밋에서 렌더링하는 데 오랜 시간이 걸린 컴포넌트를 순서대로 나열한 그래프
- **_Timeline -_** Timeline에서는 시간이 지남에 따라 컴포넌트에서 어떤 일이 일어났는 지를 확인할 수 있다.
  예를들면, input에 글자를 입력하였을 때 state의 값이 업데이트 되고, 이 값이 동기로 업데이트 되었는지, 또 언제 업데이트가 이뤄졌는지 등을 확인할 수 있다.
