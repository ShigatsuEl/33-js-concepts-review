## Closure

이번 Concept은 Closure에 관한 내용을 다뤄보려 합니다 :)<br>

MDN 공식사이트에 의하면 `Closure`는 함수와 함수가 선언된 어휘적 환경의 조합이다.<br>
...<br>
물음표 개구리 짤을 투척하고 싶다... 도대체 이게 무슨 말이냐?<br>

Closure를 이해하기 위해선 먼저 `lexical scoping`이라는 이상한 단어에 대해 미리 알아두어야 한다.<br>
다음 예제를 보겠습니다.<br>

```
function init() {
  let name = "Mozilla"; // name은 init에 의해 생성된 지역 변수이다.
  function displayName() { // displayName() 은 내부 함수이며, 클로저다.
    alert(name); // 부모 함수에서 선언된 변수를 사용한다.
  }
  displayName();
}
init();
```

위 코드를 실행하면 displayName() 함수 내의 alert()문이 부모 함수에서 정의한 변수 name의 값을 성공적으로 출력한다.<br>
여기서 "lexical"이란, 어휘적 범위 지정(lexical scoping) 과정에서 변수가 어디에서 사용 가능한지 알기 위해 그 변수가 소스코드 내 어디에서 선언되었는지 고려한다는 것을 의미한다.<br>

클로저(Closure)는 스코프(범위)에 따라서 내부함수의 범위에서는 외부 함수 범위에 있는 변수에 접근이 가능하지만 그 반대는 실현이 불가능하다는 개념이다.<br>
다음 예제를 보겠습니다.<br>

```
function makeFunc() {
  let name = "Mozilla";
  function displayName() {
    alert(name);
  }
  return displayName;
}

let myFunc = makeFunc();
//myFunc변수에 displayName을 리턴함
//유효범위의 어휘적 환경을 유지
myFunc();
//리턴된 displayName 함수를 실행(name 변수에 접근)
```

위 예제에서 displayName함수가 return 되었을 때, 보통 더 이상 makeFunc()함수의 name속성은 사용할 수 없다고 생각한다.<br>
하지만 자바스크립트는 함수를 리턴하는 순간 Closure라는 것을 생성하는데 이 클로저는 클로저가 생성될 당시의 함수와 함수가 선언된 어휘적 환경의 조합(lexical scoping)을 기억하고 있습니다.<br>
따라서 displayName 클로저는 위의 함수 형태를 그대로 기억하기 때문에 makeFunc의 name변수를 사용할 수 있는 것이다.<br>

---

### Written

- 📜 [Closures — MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Closures)

### Video

Nothing
