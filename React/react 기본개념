
[AJAX 그리고 React]
- 전통적인 웹사이트는 독립적인 HTML페이지들로 만들어졌다/
  하지만 AJAX가 생기면서 단일 페이지 앱(SPA)가 생겨나 전체 웹 애플리케이션이 한 페이지로 실행 될 수 있게 되었다. 
  
- SPA에서 브라우저는 처음에 HTML문서를 하나 적재하고,
          자바스크립트는 사용자와 애플리케이션이 상호작용하느 것에 맞춰 새 UI를 만들어주는 방법이다.
  이 때 자바스크립트는 DOM API를 사용해 브라우저의 DOM을 변경해준다.
  하지만 이 작업 시 새 엘리먼트를 추가할 때 시간이 엄청 오래 걸린다. 
  
=> 이때 브라우저의 DOM을 쉽게 갱신시켜주는 라이브러가 리액트(React)이다. 




[가상 DOM (virtual DOM)]
- 실제 DOM에 접근하는 대신, 이를 자바스크립트 객체로 구성해 추상화 하여 사용하는 방식.
- 리액트가 모든 처리를 대신 해주기 때문에 위와 같은 DOM API 조작 작업을 직접 신경 쓸 필요가 없다



[React Element (리액트 엘리먼트)]
- 가상 DOM은 리액트 엘리먼트로 이루어져 있다. 또한 브라우저 DOM은 DOM 엘리먼트로 이루어져있다.
  이 때, 리액트 앨리먼트는 그에 대응하는 실제 DOM 엘리먼트가 어떻게 생겨야하는지 기술해준다. (리액트 엘리먼트 -> DOM 엘리먼트)
  
* 리액트 엘리먼트 (React.createElement를 사용해 생성)
- React.createElement("h1", null, "신선한 사과")

* React.createElement
- 1번째 인자 : 만들려는 엘리먼트의 타입 정의
- 2번째 인자 : 엘리먼트의 프로퍼티
- 3번째 인자 : 엘리먼트의 자식 노드
 
* DOM 엘리먼트
<h1>신선한 사과</h1>

==> 둘은 같다. 리액트 엘리먼트는 단지 리액트가 DOM 엘리먼트를 구성하는 방법을 알려주는 자바스크립트 리터럴




[React DOM]
- React DOM이란 Virtual DOM에서 HTML을 생성하는데 필요한 라이브러리이다.
- React DOM에는 리액트 엘리먼트를 브라우저에 렌더링하는데 필요한 모든 도구가 들어 있다. 
- render 메소드와 서버에서 사용하기 위한 renderToString과 renderToStaticMarkup 메소드가 있다.

ex>
  var fruit = React.createElement("h1", null, "신선한 사과")
  ReactDOM.render(fruit, document.getElementById('react-container'))

* ReactDOM.render
- 1번째 인자 : 렌더링할 리액트 엘리먼트
- 2번째 인자 : 렌더링이 일어날 대상 DOM 노드

ex> 아래와 같이 HTML에 정의해둔 react-container라는 id를 가진 div의 자식으로 h1 엘리먼트가 추가된다.
  <div id="react-container">
    <h1>신선한 사과</h1>
  </div>


* 컴포넌트 트리
- ReactDOM에서 props.children을 사용해 자식 엘리먼트를 렌더링 할 수 있다. 

ex>
  React.createElement(
    "ul",
      null,
      React.createElement("li", null, "사과 1개"),
      React.createElement("li", null, "포도 2개"),
      React.createElement("li", null, "멜론 5개"),
  )
  
  4번째 이후에 추가된 인자는 다른 자식 엘리먼트로 취급된다.
  <ul>
      <li>사과 1개</li>
      <li>포도 2개</li>
      <li>멜론 5개</li>
  </ul>



=> 아래와 같이 UI엘리먼트와 데이터를 분리 할 수 있습니다. (리액트의 가장 큰 장점)
  let items = {
    "사과 1개",
    "포도 2개",
    "멜론 5개"
  }
  React.createElement("ul", {className : "ingredients"},
    items.map((ingredient, i) => 
      React.createElement("li", {key:i}, ingredient))
  )






[참고문헌]
https://withseungryu.tistory.com/56?category=878052
