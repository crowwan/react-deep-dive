
# 07장: 크롬 개발자 도구를 활용한 애플리케이션 분석

자바스크립트 이슈는 리액트 개발 도구에서 확인할 수 없다
일반적인 웹 애플리케이션 환경의 디버깅을 수행하려면 리액트 개발 도구가 아닌 좀 더 범용적인 도구를 활용해야 한다
브라우저 개발자 도구: 일반적인 브라우저 환경에서 발생할 수 있는 문제를 디버깅할 수 있는 도구

## 7.1 크롬 개발자 도구란?

크롬 개발자 도구: 크롬에서 제공하는 개발자용 도구
웹페이지에서 일어나는 거의 모든 일을 확인할 수 있다
보기 -> 개발자 도구
웹페이지에서 마우스 오른쪽 버튼 클릭 -> 검사

## 7.2 요소 탭

요소(Element)
현재 웹페이지를 구성하고 있는 HTML, CSS 등의 정보를 확인할 수 있다

왼쪽: 현재 웹페이지를 구성하는 HTML 트리 표시
원하는 태그를 클릭하면 브라우저 페이지의 해당 요소가 강조되고, 해당 태그와 관련된 정보를 확인할 수 있다
직접 코드를 수정해서 웹페이지에서 어떻게 보이는지 빠르게 확인할 수 있다
배너와 같이 코드에 의해 클래스나 속성값이 동적으로 제어되는 DOM이 있다면 요소의 중단점을 사용해 디버깅할 수 있다
중단 위치를 설정해 두면 중단과 관련된 작업이 일어날 때마다 브러우저가 렌더링을 중단하고 해당 요소 변경을 일으킨 소스코드를 보여준다
요소에 속성을 추가, 수정, 삭제하거나 해당 요소를 스크린샷으로 캡처하거나 숨기는 등 HTML DOM과 관련된 다양한 작업을 수행할 수 있다

오른쪽: 왼쪽에서 선택한 요소와 관련된 각종 정보 표시
스타일: 요소와 관련된 스타일 정보
계산됨: 해당 요소의 크기, padding, border, margin과 각종 CSS 적용 결과값
레이아웃: CSS 그리드나 레이아웃과 관련된 정보
이벤트 리스너: 현재 요소에 부착된 각종 이벤트 리스너
DOM 중단점: 중단점이 있는지 알려줌
속성: 해당 요소가 가지고 있는 모든 속성값
접근성: 웹 이용에 어려움을 겪는 장애인, 노약자를 위한 스크린리더기 등이 활용하는 값

## 7.3 소스 탭

웹 애플리케이션을 불러오기 위해 실행하거나 참조된 모든 파일을 확인할 수 있다
자바스크립트 파일, CSS, HTML, 폰트 등 다양한 파일 정보 확인 가능

소스 중단점
사용 중인 라이브러리에서 버그가 의심되는 지점을 디버깅하거나 실제로 소스코드상에서 어떤 식으로 동작하는지 확인할 수 있다
감시: 감시하고 싶은 변수를 선언하고, 해당 변수의 정보를 확인할 수 있다
중단점: 현재 웹사이트에서 추가한 중단점을 확인할 수 있다
범위: 현재 중단점에서의 스코프를 의미하며 스코프에서 접근할 수 있는 값을 확인할 수 있다
호출 스택: 현재 중단점의 콜스택을 확인할 수 있다
전역 리스너: 전역 스코프에 추가된 리스너 목록을 확인할 수 있다
XHR/가져오기, DOM, 이벤트 리스너, CSP 위반 중단점 등 다양한 중단점을 확인할 수 있다

빌드된 자바스크립트 또는 실제 개발 중인 스크립트 파일이 어떻게 실행되는지 눈으로 확인할 수 있다
변수마다 console.log로 디버깅하지 않아도 훨씬 빠르게 필요한 정보를 확인할 수 있다
현재 자바스크립트가 실행되고 있는 구조도 확인할 수 있다

## 7.4 네트워크 탭

해당 웹페이지를 접속하는 순간부터 발생하는 모든 네트워크 관련 작동이 기록된다
상단: 네트워크 탭과 관련된 다양한 메뉴를 확인할 수 있다
왼쪽: 실제 해당 페이지를 불러오는 과정에서 발생한 네트워크 요청을 볼 수 있다
하단: 페이지를 불러오는 기간동안 발생한 총 요청 건수와 총 다운로드한 업로드 리소스의 크기를 확인할 수 있다

네트워크 앱에서 집중적으로 확인해 봐야 하는 점
불필요한 요청 또는 중복되는 요청은 없는지
웹페이지 구성에 필요한 리소스 크기가 너무 크지 않은지
리소스를 불러오는 속도는 적절한지 또는 너무 속도가 오래 걸리는 리소스는 없는지
리소스가 올바른 우선순위로 다운로드되어 페이지를 자연스럽게 만들어가는지

## 7.5 메모리 탭

현재 웹페이지가 차지하고 있는 메모리 관련 정보를 확인할 수 있다
애플리케이션에서 발생하는 메모리 누수, 속도 저하, 혹은 웹페이지 프리징 현상을 확인할 수 있는 유용한 도구이다

프로파일링 작업을 거쳐야 원하는 정보를 볼 수 있다
힙 스냅샷: 현재 메모리 상황을 사진 찍듯이 촬영할 수 있다
타임라인의 할당 계측: 시간의 흐름에 따라 메모리 변화를 확인할 수 있다
할당 샘플링: 메모리 공간을 차지하고 있는 자바스크립트 함수를 볼 수 있다