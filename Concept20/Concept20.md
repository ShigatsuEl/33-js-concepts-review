## 순수함수, 부수효과, 상태변이

이번 Concept은 순수함수 / 부수효과 / 상태변이에 대한 이야기 입니다.<br>

20번 컨셉에서 다룰 이야기는 아무래도 자바스트립트의 유지보수에 대한 이야기 같다.<br>
아무래도 자바스크립트는 다른 언어와 다르게 코드 한 줄이 어떨 땐 타입이 이거였다 갑자기 저거였다 식으로 바뀌기도 하기 때문에..<br>
자바스크립트 개발자는 항상 이 부분을 두려워 하는 듯함.<br>
때문에 타입스크립트로 넘어가는 것이고..?<br>
타입스크립트를 한번 써 본 사람들은 다시 자바스크립트로 돌아오지 않는다고 하던데 ㅠㅠ 이번 컨셉을 다뤄보면서 자바스크립트의 유동적인 부분에 대해 생각해보기로 한다.<br>

순수함수

먼저 순수함수라는 것은 함수 밖에 있는 값들은 일절 변경하지 않는 것을 말하는 것 같다.<br>
예를 들어

```
let values = { a: 1 }

function impureFunction(items) {
  let b = 1

  items.a = items.a * b + 2

  return items.a
}

let c = impureFunction(values)
// Now `values.a` is 3, the impure function modifies it.
```

위의 코드는 함수가 values객체의 a값을 바꾸어버렸습니다.<br>
함수 바깥의 값을 함수로 인해 바꿔버렸으니 이것은 순수함수가 아닙니다.<br><br>

```
var values = { a: 1 }

function pureFunction(a) {
  var b = 1

  a = a * b + 2

  return a
}

var c = pureFunction(values.a)
// `values.a` has not been modified, it's still 1
```

이번 방법은 함수 바깥의 값을 변경하지 않으며 함수 내 자체에서 값을 수정합니다.<br>
이것이 순수함수라고 할 수 있습니다.<br>
또한 이렇게 순수함수를 통해 프로그래밍 하는 것을 함수형프로그래밍(Functional Programming)이라고 합니다.<br>
순수함수를 사용하는 것이 불순수함수를 사용하는 것 보다 에러도 적게 나고 코드 유지보수에도 당연히 좋겠쥬?<br><br>

부수효과

부수효과는 위에서 설명한 덕분에 쉽게 정리할 수 있습니다.<br>
부수효과는 위에서 함수 외부의 값을 변경하는 경우를 말합니다.<br>
마치 불순수함수라고도 할 수 있겠네용!<br>
부수효과는 당연히..? 자제할 수 있으면 적게 쓰는 편이 좋습니다.<br><br>

상태변이

자바스크립트에서 상태변이를 생각해보자면, 자바스크립트는 변이에 가까울지 불변에 가까울지를 먼저 생각해보기로 합니다.<br>
자바스크립트가 갖는 타입은 총 2가지로 나뉘는데 primitive type | reference type입니다.<br>
primitive type은 변경될 수 있음은 물론이고 reference type 역시 참조로 얼마든지 변경할 수 있습니다.<br>
자바스크립트는 이렇듯 불변이라는 단어와는 거리가 먼 개념입니다.<br>
왜냐하면 자바스크립트는 런타임 언어이기 때문입니다.<br>
어떠한 값에 대해 아무리 안전하게 설정을 했다고 해도 안 바뀔 것이라는 장담을 할 수도 없습니다.<br>
특히나 코드의 많은 부분을 참조로 사용하게 되면 부작용이 발생하며 원치 않는 결과들을 불러일으키ㅣ도 하죠<br>
어디에서 변경되었는지, 정확히 무엇이 변경되었는지 무엇 하나 쉽게 대답할 수도 없고 말입니다.<br>

그래서 우리가 해야하는 것은 가치 지향 프로그래밍입니다.<br>
Object.freeze | const 등은 이렇게 원천을 차단해 값이 변경되는 것을 방지하기 때문에 유지보수에도 좋으며 우리가 앞으로 목표로 해야할 것 입니다.<br>

---

### Written

- 📜 [Pure functions in JavaScript — @nicoespeon](https://www.nicoespeon.com/en/2015/01/pure-functions-javascript/)

- 📜 [The State of Immutability — Maciej Sikora](https://medium.com/dailyjs/the-state-of-immutability-169d2cd11310)

### Video

Nothing
