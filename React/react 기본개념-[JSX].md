<br/>

### JSX란?

React.createElement를 번거롭게 입력하는 대신 사용할 수 있는 대안이다.
자바스크립트의 확장으로 HTML과 비슷한 구문을 사용해 정의 할 수 있다.

    리액트 엘리먼트 : React.createElement(IngredientList, {list:[...]});
     =>
    JSX : <IngredientsList list={[...]} />

<br/>

---

#### JSX 사용

* 내포된 컴포넌트

JSX에서는 다른 컴포넌트의 자식으로 컴포넌트를 추가할 수 있다.

    <IngredientsList>
      <Ingredient />
      <Ingredient />
      <Ingredient />
    </IngredientsList>


<br/><br/>

* className 

자바스크립트에서는 class가 예약어이기 때문에 class 대신 className을 사용한다.

    <h1 className="hi">Hellow World</h1>
    
 
<br/><br/>

* 자바스크립트 식

식을 중괄호로 감싸면 안의 식을 평가해서 결괏값을 돌려주어야 한다는 뜻이다.

    <h1>{this.props.title}</h1>
    
    
문자열이 아닌 다른 타입의 값도 자바스크립트 식 안에 넣어야 한다.
    
    <input type="checkbox" defaultChecked={false} />
 
 
 
<br/><br/>
 

*  JSX로 배열 매핑

JSX는 자바스크립트이기 때문에 함수 안에서 JSX를 직접 사용할 수 있다.

    <ul>
      {this.props.ingredients.map((ingredient, i) => 
              <li key={i}>{ingredient}</li>
         )}
    </ul>
    
 
 
 
 
 <br/><br/>
---

[참고문헌]
https://withseungryu.tistory.com/60?category=878052
