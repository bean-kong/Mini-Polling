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
