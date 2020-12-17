## React Study

### JSX

```javascript
const element = <h1>Hello, world!</h1>;
```

: 위와 같은 형태를 JSX라고 하고 Javascrpit를 확장한 문법이야. 
  
  JSX의 중괄호 안에는 유효한 모든 JavaScript 표현식을 넣을 수 있어.
  예를들어
  ```javascript
  const name = 'sung bin';
  const element = <h1> hi {name}</h1>;
  ```
  
  이런식으로 말야
  
  <br/>
  
  **JSX도 표현식이야**
 
 : 컴파일이 끝나면, JSX표현식이 정규 Javascript함수 호출이 되고 Javascript 객체로 인식되어져.
 
 즉, JSX를 if 구문 및 for loop 안에 사용하고, 변수에 할당하고, 인자로 받아들이고, 함수로 부터 반환이 가능하다 이말이야.


<br/>



**JSX 속성정의**

: 속성에 따옴표를 이용해 문자열 리터럴을 정의할 수 있어.
```javascript
const element = <div tabIndex="0"></div>;
```

이런식으로말야

또 중괄호를 사용해서 어트리뷰트에 javascript 표현식을 삽입할 수도 있어
```javascript
const element = <img src={user.avaarUrl}></img>;
```

<br/>



**JSX로 자식 정의**

: JSX태그는 자식을 포함할 수 있어. 즉 아래처럼 가능하다는거지
```javascript
const element = (
  <div>
     <h1>Hello!!<h1/>
  </div>
```
<br/>



**JSX는 주입 공격을 방지해줘**

: JSX에 사용자 입력을 삽입하는 것은 안전하데
  
  기본적으로 React DOM은 JSX에 사입된 모든 값을 렌더링하기 전에 이스케이프 하기에, 애플리케이션에서 명시적으로 작성되지 않은 내용은 주입되지 않는데. 그래서 XSS(cross site scripting) 공격을 방지할 수 있떼. 얘는 또 뭐지
  
  <br/>
  
  
  
 #### 에릴먼트 렌더링
 
 : 엘리먼트는 React 앱의 가장 작은 단위야. 엘리먼트는 화면에 표시할 내용을 기술한다고 생각하면 되.
 
 React 엘리먼트는 불변객체야. 엘리먼트를 생성한 이후에는 해당 엘리먼트의 자식이나 속성을 변경할 수가 없어. 그렇기에 현재까지 내용들을 바탕으로는 생각해보면 UI를 업데이트하는 유일한 방법은 새로운 엘리먼트를 생성하고 이를 ReactDOM.render()로 전달하는거네. 하지만 이때 전체 UI가 다시그려지는건 아니야!! ReactDOM은 내용이 변경된 놈에 대해서만 업데이트 해줘
 
 <br/>
 
 
 
 #### 컴포넌트 

: 리액트에서 재사용할 수 있는 UI를 하나의 묶음으로 컴포넌트라고 해! 즉 엘리먼트의 조각들을 모아 모듈화한것을 의미한다고 볼 수 있어. 그리고 이 컴포넌트에는 Function Component와 Class Component 두가지가 존재해.

개념적으로 컴포넌트는 Javascript 함수와 유사해. props라고 하는 임의의 입력을 받은 후 화면에 어떻게 표시되는지를 기술하는 React 엘리먼트를 반환하는거야.

<br/>

* 함수컴포넌트

```javascript
function Welcome(props){
  return <h1>Hello, {props.name}</h1>;
}
```

이 함수는 데이터를 가진 하나의 props객체 인자를 받은 후 React엘리먼트를 반환하므로 유효한 React 컴포넌트야. 이런 컴포넌트는 Javascript 함수이기때문에 말 그대로 함수 컴포넌트라고 호칭해


* 클래스 컴포넌트
```javascript
class Welcome extends React.Componenet{
  render() {
    return <h1>Hello, {this.props.name}</h1>;
    }
 }
 ```
 이렇게 ES6 Class를 사용하여 컴포넌트를 정의할 수 있고 이런 형태를 클래스 컴포넌트라고해.
 
 참고로 React의 관점에서 보면 두가지 유형의 컴포넌트는 동일해.

<br/>



**컴포넌트 렌더링**

: React 앨리먼트는 사용자 정의 컴포넌트로도 나타낼 수 있어. 예를들어 아래처럼
```javascript
const element = <Welcome name="Sara"/>;
```
React가 사용자 정의 컴포넌트로 작성한 엘리먼트를 발견하면 JSX 어트리뷰트와 자식을 해당 컴포넌트에 단일 객체로 전달해. 이 객체를 'props'라고 해.
