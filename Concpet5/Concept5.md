## == vs === vs typeof

저번 강의에서 `Type Coercion`에 대해서 알아보았습니다.<br>
이번 강의에서는 'Type Coercion'과 관련된 == & === 에 관하여 알아보려 합니다.<br>

== 와 === 의 차이가 무엇일까요?<br>
4번 컨셉에서도 언급한 내용이지만 자바스크립트는 타입이 다른 것들끼리 무엇인가 하려고 하면 자동적으로 타입을 원하든 원치않든 변경하여 'Type Coercion'이 일어난다고 했습니다.<br>
== 와 === 의 차이점은 이 'Type Coercion'이 일어나는지 안 일어나게 하는지에 따라 달렸습니다.<br>

밑의 코드로 이동하겠습니다.<br>
```
'1' == 1
'1' === 1
```

똑같아 보이지만 조금 다른 두 줄의 코드가 있습니다.<br>
이 코드의 결과는 어떻게 나올까요?<br>
```
true
false
```
위에 식은 true가 나오고 밑의 식은 false라는 결과가 나옵니다.<br>
여기서 == 와 === 의 차이점을 알 수 있습니다.<br>

1. == 는 'Type Coercion'을 발생시켜 타입이 달라도 변형이 되어 결과가 도출됩니다.
2. === 는 'Type Coercion'이 발생하지 않아 타입이 달라도 변형하지 않고 결과가 도출됩니다.

따라서 위의 식은 '1' 문자열이 숫자 1로 변경되어 값이 서로 같다(true)가 나오고 아래 식은 변형되지 않아 '1'(String)과 1(Number)는 같지 않다고 결론 지은 것입니다.<br>
이해가 가지 않는다면 저번 컨셉에 대해 참고하시는 것을 추천합니다.<br>

결론!<br>
== 와 === 의 차이점을 알고 그에 맞게 쓸 줄 알아야 한다.<br>
=== 을 사용하기를 권장합니다 :)<br><br>

다음으로 알아볼 것은 `typeof`입니다.<br>
자바스크립트는 type이 런타임으로 동작하기 때문에 항상 type이 무엇인지 확인을 해야합니다.<br>
이것을 가능하게 하는 친구가 `typeof`입니다.<br>
'typeof'는 대부분의 prinitive value에서 적용이 됩니다.
```
typeof '1' // -> string
typeof 1 // -> number
typeof true // -> boolean
typeof function(){} -> funcion
```
이렇게 유용하게 사용되는 친구이지만 오류를 일으키는 경우도 있습니다.
```
typeof null // -> object
```
null 타입이 object라뇨?? 되게 신기한 결과가 나오는 군요 ㄷ.ㄷ<br>
이것은 자바스크립트 개발을 맡은 사람들이 null으로 오류를 고치게 될 시 다른 많은 프로그램에 영향을 미치게 된다하여 고치지 않았다고 합니다.<br>
따라서 reference type들은 typeof를 사용하는 것이 아닌 `instanceof`를 사용하는 것을 추천합니다.<br>
'instanceof'는 primitive type에서 작동하지 않습니다.<br>

결론<br>
1. primitive type은 `typeof`를 사용할 것!
2. reference type은 `instanceof`를 사용할 것!
   
---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [Checking Types in Javascript — Toby Ho](http://tobyho.com/2011/01/28/checking-types-in-javascript/)

### Video

Nothing
