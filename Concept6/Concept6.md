## 함수 범위, 블록 범위, 렉시컬(lexical) 범위

이번 Concept은 `Scope`에 대해서 알아보겠습니다.<br>

Scope는 자바스크립트에서 변수가 어디까지 접근이 가능한지를 정의합니다.<br>
Scope는 크게 2가지로 분류할 수 있습니다.<br>

1. Global Scope
   
   변수가 함수 바깥이나 {}(컬리 브라켓) 바깥에 선언되어 있다면 이것은 `Global Scope`에 정의되었다고 합니다.<br>
   글로벌 스코프로 선언이 되면 코드 내 어디서든 사용이 가능합니다. 밑의 코드처럼 말이죠.<br>
   ```
   const hello = 'Hello CSS-Tricks Reader!'

   function sayHello () {
     console.log(hello)
   }
   
   console.log(hello) // 'Hello CSS-Tricks Reader!'
   sayHello() // 'Hello CSS-Tricks Reader!'
   ```
   글로벌 스코프는 이렇게 전역적으로 사용이 가능하지만 코드를 실행하는 즉시 메모리에 변수가 올라가서 끝날 때까지 존재하기 때문에 가급적이면 지역 변수를 사용하는 것이 좋습니다.<br>

2. Local Scope
   
   변수를 특정한 부분에 선언을 하는 것을 `Local Scope`라고 합니다.<br>
   'Local Scope'는 크게 2가지로 분류됩니다.<br>

   1. Function Scope
      함수 안에 변수를 선언하는 것입니다.<br>
      Scope가 함수 안에서만 움직이고 바깥에서는 사용할 수 없습니다.<br>
      ```
      function sayHello () {
      const hello = 'Hello CSS-Tricks Reader!'
      console.log(hello)
      }

      sayHello() // 'Hello CSS-Tricks Reader!'
      console.log(hello) // Error, hello is not defined
      ```

   2. Block Scope
      {}(컬리 브라켓)안에 변수를 선언하면 {}안에서만 변수를 사용할 수 있습니다.<br>
      ```
      {
      const hello = 'Hello CSS-Tricks Reader!'
      console.log(hello) // 'Hello CSS-Tricks Reader!'
      }

      console.log(hello) // Error, hello is not defined
      ```
      <br>

Hoisting도 간략하게 다뤄보겠습니다.<br>
호이스팅은 함수가 선언하게 되면 자동으로 코드의 가장 위에서 선언되는 것 입니다.<br>
때문에 밑의 코드와 같이 위의 식과 아래 식은 똑같이 작동합니다.<br>
```
sayHello()
function sayHello () {
  console.log('Hello CSS-Tricks Reader!')
}

// This is the same as the code above
function sayHello () {
  console.log('Hello CSS-Tricks Reader!')
}
sayHello()
```
따라서 호출을 위에서 하던지 아래에서 하던지 상관이 없는 것 입니다.<br>
중요한 점은 함수를 declaration하면 호이스팅이 되지만 expression하면 호이스팅이 되지 않습니다.<br>
이렇게 호이스팅을 사용할 때도 있고 아닐 때도 있기 때문에 호이스팅은 가급적 사용하지 않는 것이 좋으며 함수를 사용하기 전에 선언하는 것을 추천합니다.<br><br>

Nested Scope<br>

함수 안에 함수가 선언된 것을 말합니다. 다른 표현으로는 중첩되었다고 할 수 있습니다.<br>
```
function outerFunction () {
  const outer = `I'm the outer function!`

  function innerFunction() {
    const inner = `I'm the inner function!`
    console.log(outer) // I'm the outer function!
  }

  console.log(inner) // Error, inner is not defined
}
```
이렇게 안의 함수가 밖에 있는 함수의 변수를 사용하는 것을 `lexical scoping`이라고 합니다.<br>
안에서는 바깥의 변수를 사용할 수 있는데 바깥에서는 안에 있는 함수의 변수를 사용할 수 없는 것 입니다.<br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [JavaScript Scope and Closures — Zell Liew](https://css-tricks.com/javascript-scope-closures/)

### Video

Nothing


