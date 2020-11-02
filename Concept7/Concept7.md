## 식(expression) vs 문(statement)

이번 Concept은 Function Declarations vs. Function Expressions를 다뤄보려 합니다.<br>
Function Declaration은 무엇이며 Funcion Expressions는 무엇일까요?<br>

1. Function Statement
   
   `Function statement`는 함수를 선언합니다.<br>
   이렇게 선언된 함수들은 나중에 호출이 되면 사용이 되어집니다.<br>
   함수 선언의 모양새는 이렇습니다.<br>
   ```
   function bar() {
     return 3;
   }
   ```

2. Function Expression
   
   `Function Expression`은 함수를 선언할 수 있는 또 다른 방법입니다.<br>
   함수 표현식은 함수를 선언하지 않고 변수에 값으로 할당합니다.<br>
   이렇게 할당된 변수는 마치 함수처럼 사용할 수 있습니다.<br>
   나중에 변수가 호출되면 함수가 호출되는 것처럼 작동하는 것이죠!<br>
   ```
   const a = function(x, y) {
     return x * y;
   }

   // 이것은 아래처럼 간결하게 표현할 수도 있습니다.
   const a = (x, y) => x *y

   // 또한 나중에 함수처럼 호출을 할 수도 있습니다.
   a(1, 2);
   ```
   <br>

그렇다면 Function statement 와 Function expression의 차이점은 무엇일까요?<br>

1. declaration은 함수가 호이스팅이 되기 때문에 어디서든지 호출해도 상관이 없습니다.<br>
   반면에 expression은 함수가 변수에 값이 들어가기 때문에 호이스팅이 되지 않으며 값이 선언되고 나서야 호출을 할 수 있다는 점이 있습니다.<br>

1. declaration은 코드가 실행되기 전에 로드 되지만 expression은 인터프리터가 호출할 때 되어서야 로드를 합니다.

가급적이면 expression을 사용하는 것이 유지보수에 좋습니다.<br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [Function Declarations vs. Function Expressions — Mandeep Singh](https://medium.com/@mandeep1012/function-declarations-vs-function-expressions-b43646042052)

### Video

Nothing
