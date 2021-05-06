
### React 기본개념 - [컴포넌트]
<br/>

---
<br/>

#### [컴포넌트]
컴포넌트를 사용하면 서로 다른 데이터 집합에 같은 DOM 구조를 재사용할 수 있어야 한다.
리액트로 UI를 구상할 때, 엘리먼트를 재사용할 수 있는지 고려해야한다.


컴포넌트는 객체이다. 따라서 일반 자바스크립트 클래스와 마찬가지로 내부에 코드를 캡슐화 할 수 있다.


<br/>

###### [리액트에서 컴포넌트를 만드는 3가지 방법]
1. createClass를 사용하는 방법
2. ES6 Class를 사용하는 방법
3. 상태가 없는 함수형 컴포넌트를 사용하는 방법

<br/>

###### [ React.createClass (createClass를 사용하는 방법) ]
리액트가 처음 만들어졌을 때의 유일한 방법이었다.

    const FruitList = React.createClass({
      displayName: "FruitList"
        render(){
        return React.createElement("ul", {className: "fruits"},
                                  this.props.items.map((fruit, i) => React.createElement("li", {key: i}, fruit)
                                                      )
                                  )
      }
    })

    const items = {
        "사과 1개",
        "포도 2개",
        "멜론 5개"
    }

    ReactDOM.render(
      React.createElement(FruitsList, {item}, null),
        document.getElementById('react-container')
    )
    
    
    <FruitsList items =[...]>
      <ul classname = "fruits">
            <li key="0">사과 1개</li>
            <li key="1">포도 2개</li>
            <li key="2">멜론 5개</li>
      </ul>
    </FruitsList>


<br/>

###### [ React.Component (ES6 클래스를 사용하는 방법) ]
ES6의 클래스 선언이다.
리액트 컴포넌트를 새로 만들 때 React.Component를 추상 클래스로 사용 할 수 있다.
ES6 구문으로 추상 클래스를 상속하면 커스텀 컴포넌트를 만들 수 있다.

    class FruitsList extends React.Component {
        renderListItem(ingredient, i){
            return React.createElement("li", { key: i}, fruit)
        }
        render(){
            return React.createElement("ul", {className: "fruits"},
                                        this.props.items.map(this.renderListItem)
                                      )
        }
    }




<br/>

###### [ 함수형 컴포넌트 ]

객체가 아닌 함수이다.
프로퍼티를 인자로 받아서 DOM 엘리먼트를 반환하는 함수이다.
코드가 더 단순해지고, 코드베이스를 훨씬 더 잘 테스트 할 수 있습니다. 아키텍쳐를 단순하게 유지 할 수 있다.
다른 컴포넌트 방법보다 성능이 우수하다. 하지만 캡슐화해야 하거나 this가 필요하면 사용 할 수 없다.
state를 갖지 못하며, life-cycle 함수 사용이 불가능하다

    const fruitsList = props =>
      React.createElement("ul", {className: "fruits"},
                           props.items.map((fruit, i) =>
                                          React.createElement("li", {key: i}, fruit)
                                          )
                           )




<br/>

###### [ 클래스 컴포넌트 VS 함수형 컴포넌트 ]

함수형의 코드가 더 단순하며 간결하다. 속도도 더 빠르다
하지만 함수형은 state, this, life-cycle 함수를 사용 할 수 없다.



<br/>

---




[참고문헌]
https://withseungryu.tistory.com/58?category=878052
