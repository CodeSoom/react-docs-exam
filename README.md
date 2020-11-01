# 리액트 문서 스터디 질문모음집

https://reactjs.org/docs

## 1. Hello World

* 다음 함수를 실행하면 어떤 일이 발생하나요?

```js
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root'),
);
```
## 2. Introducing JSX

* React는 마크업과 로직 두 가지를 모두 포함하는 [ㅇㅇㅇㅇ]라고 하는 느슨하게 결합 된 단위로 관심사를 분리합니다.
* JSX는 무엇인가요?
* JSX는 어느 시점에서 React.createElement()로 변경 될까?
* JSX를 표현식으로 취급하고 반복문, 조건문 등에 사용할 수 있는 이유는 JSX가 기본적으로 (자바스크립트 객체)이기 때문이다.
* JSX의 장점은 무엇이 있는가?

## 3. Rendering Elements

* 리액트에서 elements는 imutable입니다. 그렇다면 UI를 업데이트하려면 어떻게 해야되나요?
* 다음 구문을 실행하면 1초마다 모든 부분이 reRender 되나요? (O, X)

```js
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );

  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```
* 왜 react는 직접 DOM을 조작하지 않고 VDOM을 사용할까?
* 리액트 엘리먼트는 (불변) 자바스크립트 객체다.
* React DOM은 어떤 경우에만 DOM을 업데이트 하나요?
* 엘리먼트는 컴포넌트인가?

## 4. Components and Props

* 무언가를 인자로 받아서 무언가를 반환하는 function으로 리액트의 컴포넌트를 바라봤을 때 어떤 닮은 점이 있을까요?
* props를 다룰 때는 순수함수처럼 다뤄야 합니다.(O, X)
* ReactComponent의 입력 값과 반환 값을 뭐라고 부를까?
* 리액트 컴포넌트는 (props)를 인자로 받고 화면에 어떻게 보일지 기술하는 (리액트 엘리먼트)를 반환하는 (자바스크립트 함수)다.
* React 컴포넌트가 props를 다룰 때 어떻게 동작해야 하나요?

## 6. State and Lifecycle

* 데이터의 흐름이 위에서 아래로 흐른다는 것은 무엇을 뜻하나요?
* 비동기적으로 처리되기 때문에 다음 state를 계산할 때 해당 값에 의존해서는 안 됩니다.(O, X)
* 클래스 컴포넌트의 setState() 메서드와 setState() 훅의 state 갱신 방식 차이는?
* state를 다룰 때 주의 사항 세가지는?
* 마운트란 무엇인가요?

## 7. Handling Events

* DOM event linster 와 차이점은 무엇인가요?
* 익명함수로 이벤트 핸들링을 하면 render시 마다 매번 새로운 함수 할당 안 해도 되는 하위 props rerendering이 일어날 수도 있습니다.(O, X)
* React와 브라우저 Element 이벤트 처리 방식의 차이는?
* 클래스 컴포넌트에서 이벤트 핸들러에 콜백을 사용하고 자식 컴포넌트에게 전달할 경우 (콜백이 매번 생성된다)
* onClick의 매개변수(?) e는 무엇인가?
## 7. Conditional Rendering

* 조건에 따라 컴포넌트를 보여주기위해서 어떻게 할 수 있나요?
* props.warn 이 false일때는 rednering하지 않게 하려면 어떻게 할 수 있을까요?

```js
function WarningBanner(props) {
  return (
    <div className="warning">
      Warning!
    </div>
  );
}
```

* 개인적으로 가장 많이 사용하는 조건부 렌더링 방식과 이유를 설명하라.
* 조건부 렌더링은 자바스크립트에서 사용하는 (조건문), (조건부 연산자)를 사용할 수 있다.
* 컴포넌트의 render 메서드로 null을 반환하는 것은 어떤 경우이며, 이는 생명주기 메서드 호출에 영향을 주는가?

## 8. Lists and Keys

* list rendering 할 때 key를 넣어주는 이유가 뭘까요?
* 키를 인덱스로 처리하는 것이 안티 패턴인 이유는?
* 리액트에서 반복되는 컴포넌트는 반드시 (key)를 갖고 있어야 한다.
* keys의 존재 이유는?
* key에 인덱스를 사용하는 것을 권장하지 않는 이유

## 9. Forms

* controlled components 와 uncontrolled component에 대해서 설명해주세요
* 다른 엘리먼트와 폼 엘리먼트의 차이점은?
* 리액트 폼은 HTML과 다르게 (제어 컴포넌트) 개념을 사용한다.

## 10. Lifting State Up

* state를 올려서 상위에 받는 방법에 대해서 설명해주세요
* 이 방법에 장점 단점은 뭐가 있을까요?
* State 끌어올리기란?
* 리액트에서 상태 관리는 데이터 동기화 보다 (하향식 데이터 흐름)에 의존하길 강조한다.
* state를 끌어올리는 작업의 장점

## 11. Composition vs Inheritance

* composition으로 새로운 컴포넌트를 어떻게 만들 수 있나요?
* 왜 리액트에서는 합성을 권장할까?
* 리액트에서는 컴포넌트를 재사용할 때 (상속)보다 (합성)을 훨씬 권장한다.
* 합성과 상속의 차이

## 12. Thinking In React

* 리액트로 웹 개발하는 방법에 대해서 설명해 주세요
* State로 쓸지 말지 구별하려면 어떤 판단 기준이 있나?
* 정적인 버전 리액트를 개발할 때는 (state)는 필요 없다. (props)를 통해서만 구현할 수 있도록 진행 후 (state)가 꼭 필요한 부분에만 사용하자.
* state를 어디에 두어야 할지 고민할 때 좋은 세 가지 질문은?
* React로 App을 설계하는 5단계의 방식
 
## Accessibility

* 접근성을 높이려면 어떻게 봐꿔줘야 할까요?
```html
<label>Name:</label>
<input id="namedInput" type="text" name="name"/>
```
* 웹 접근성이란 무엇인가?
* 포커스 컨트롤이란 무엇인가?

## Code-Splitting

* code splitting을 하여 얻는 이점은 무엇인가요?

## Context

* createContext에서 기본값은 왜 주어야 하나요?
* 왜 context를 남용하면 컴포넌트 재사용이 어려워질까?
* context를 사용할 때 주의해야 할 점

## Error Boundaries

* Error Boundaries가 이벤트 핸들러에서는 동작하지 않는 이유는?
* 에러 경계와 try/catch 구문과의 차이점은?
* 에러 경계는 이벤트 핸들러에서 발생하는 에러도 잡아낼 수 있는가?
* Error Boundaries는 무엇인가?

## Forwarding Refs

* 왜 React.forwardRef는 단절적인 업데이트로 간주해야 할까?
* ref는 언제 사용하면 좋은가?

## Fragments

* Fragments를 사용하는 이유는?
* <></> 와 Fragments 차이에 대해서 설명해주실래요?
* 왜 fragment를 사용하나?
* Fragments가 하는 역할은?
* <React.Fragment> 문법으로 명시적으로 선언하는 상황은 어떨 때 인가?
## Higher-Order Components

* HOC는 왜 유용하고 어떻게 만들 수 있나요?
* 일반 컴포넌트와 HOC의 차이는?
* HOC의 장, 단점

Integrating with Other Libraries

## JSX In Depth

* React Element의 타입을 결정하는 건 JSX의 어느 부분?
* JSX에서 Props의 기본값은 무엇인가?

## Optimizing Performance

* 성능 최적화 방법들은 무엇이 있는가?

## Portals

* 왜 Portals를 이용해도 이벤트 전파가 기대한 대로 잘 일어 날까?
* Portal은 무슨 역할을 하는가?

