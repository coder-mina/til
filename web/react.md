@ This document is a summary (without paraphrasing) of React official Docs (https://reactjs.org/docs/). @

# 내가 모르는 것

* DOM 이 무엇? DOM node이 무엇?
* 리액트 element가 정확히 뭐임?? 그냥 변수인가??
* JSX 에서 태그 내에서 JS 나타내려면 {} 안에 표시하는 건가???

# React

* React는 JavaScript library이다.

## Introducing JSX

* JSX = syntax extension to JavaScript.
  
* funny tag syntax 
  
    ```js
    const element = <h1> Hello </h1>;
    ```

## Rendering Elements

* `Elements` are the smallest building blocks of React apps. React elements are plain objects.

* HTML 파일에 <div id="root"></div> 이렇게 있다고 하면 이것은 `root DOM node`라고 부른다!!! 

* Applications built with just React usually have a single root DOM node.

* To render a React element into a root DOM node, pass both to ReactDOM.render()

  ```js
  const element = <h1>Hello, world</h1>;
  ReactDOM.render(element, document.getElementById('root'));
  // 첫 번째 인자 = JSX, React element
  // 두 번재 인자 = 해당 요소를 렌더링하고 싶은 컨테이너
  ```

* rendering = html element, react element 등의 코드가 눈으로 볼 수 있도록 화면에 그려지는 것.
* React elements are `immutable`. So, the only way to update the UI is to create a new element and pass it to ReactDOM.render()



## Components and Props

* Conceptually, components are like JS functions. They accept arbitrary inputs (called props) and return React elements.

* How to define a component

  * 1. function component

       ```js
       function Welcome(props) {
         return <h1>Hello, {props.name}</h1>;
       }
       ```

    2. class component

       ```js
       class Welcome extends React.Component {
         render() {
           return <h1>Hello, {this.props.name}</h1>;
         }
       }
       ```

* Revisiting React elements

  * 1. React elements that represent DOM tag

       ```js
       const element = <div />;
       ```

    2. React elements that represent user-defined components.

       ```js
       const element = <Welcome name="Sara" />;
       ```

       ```js
       function Welcome(props) {
         return <h1>Hello, {props.name}</h1>;
       }
       const element = <Welcome name="Sara" />;
       // React calls the Welcome component with {name: 'Sara'} as the props.
       // Welcome component returns <h1>Hello, Sara</h1> element as the result.
       ReactDOM.render(
         element,
         document.getElementById('root')
       );
       ```

       When React sees an element representing a user-defined component, it passes JSX attributes to this component as a single object (= `props`)

* React treats components starting with lower-case letters as DOM tags (built-in components like <div> or <span>)
* User-defined components should start with a capital letter.



* Components can refer to other components in their output.
* Typically, new React apps have a single App component at the very top.
* Name props from the component's own point of view rather than the context in which it is being used.
* Split components into reusable chunks! 
* All React components should never modify its own props. (= act like pure functions with respect to their props.) Props are read-only.

  ```
component = 붕어빵 틀, element = 각 붕어빵, props = 붕어빵에 들어가는 재료

* component = 재사용 가능한 UI 단위, React.Component를 extend해서 class로 컴포넌트 생성하며 이때 render() 메소드를 정의하는 것은 필수. 
* props = component의 속성.
* state = component의 상태값.
  ```



## State and Lifecycle

* State allows React components to change their output over time in response to user actions, network responses, and anything else, without violating the rule - props are read only.