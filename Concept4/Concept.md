## 명시적 변환, 암시적 변환, Nominal, 구조화, 덕 타이핑

이번 Concept에서는 Type Coercion이라는 띠용하는 친구에 대해 알아보겠습니다.<br>

```
console.log(4 + "hello");
console.log(4 + 4 + "hello");
console.log("" == true);
console.log(1 == true);
console.log(66 + true);
```

위의 코드를 봅시다. 타입이 서로다른 아이들로 어떠한 작업을 하고 있는데요~ 보통 다른 프로그래밍 언어에서는 이렇게 타입이 다른 것들끼리 무엇인가 할 수 있게 되어 있지 않습니다.<br>
하지만 자바스크립트는 위의 코드가 가능합니다. 자바스크립트가 맘대로 바꿔서 말이죠!<br>
위의 결과는 아래와 같이 나옵니다.
```
4hello
8hello
false
true
67
```
신기하네용ㅋ.ㅋ 어떻게 이러한 결과가 나왔는지를 지금부터 설명해보자 합니다.<br>

자바스크립트는 타입이 서로 다른 것들끼리 무엇인가 하려고 하면 자기 입맛에 맞춰 자동적으로 변환을 하는 작업을 하는데요.<br>
이것을 `Type Coercion`이라고 합니다.<br>
위 결과에서 사실은 이렇게 동작하게 되는 것이죠.<br>
```
4hello -> 숫자 4를 String 4로 변환하여 hello와 합침
8hello -> 숫자 4와 4를 먼저 더한 후 String으로 변환하고 hello와 합침
false -> ""(빈 스트링)은 false로 변환되어 false값이 나옴
true -> 숫자 1은 true로 변환되어 true값이 나옴
67 -> true는 숫자 1로 변환되어 더해져서 67이 나옴
```

자바스크립트는 이렇게 타입이 다른데도 불구하고 'Type Coercion'이 일어나서 에러가 일어나지 않게 되죠.<br>
좋은 경우도 있으나 이것으로 인해 에러를 찾기 힘든 경우도 생깁니다.<br>
이 컨셉에 대해 알아두면 자신이 원하는 결과값과 다른 결과를 발견했을 때 보이지 않는 오류를 찾는 데 도움이 될 것 입니다.<br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [What you need to know about Javascript's Implicit Coercion — Promise Tochi](https://dev.to/promhize/what-you-need-to-know-about-javascripts-implicit-coercion-e23)

### Video

Nothing