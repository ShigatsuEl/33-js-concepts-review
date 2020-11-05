## 부분 어플리케이션, 커링(Currying), Compose, Pipe

이 Concept은 커링 & Compose & Pipe에 관해서 간략히 다뤄보도록 하겠습니다.<br>

### Currying

하나 이상의 인수의 함수를 하나의 인수의 함수로 줄이는 방법이 있습니다.<br>
이것을 커링이라고 합니다.<br>

Currying은 람다 미적분학의 도움을 받아 하나 이상의 인수의 함수를 하나의 인수의 함수로 줄이는 프로세스입니다.<br>

```
multiply = (n, m) => (n * m)
multiply(3, 4) === 12 // true

curryedMultiply = (n) => ( (m) => multiply(n, m) )
triple = curryedMultiply(3)
triple(4) === 12 // true
```

반대로 Uncurrying도 있습니다.<br>

```
curryedMultiply = (n) => (m) => n * m
curryedMultiply(3)(4) === 12 // true

multiply = (n, m) => curryedMultiply(n)(m)
multiply(3, 4) === 12 // true
```

### Pipe

pipe는 데이터형을 원하는 형태로 바꾸거나 생성하기 위해 액션 하나하나를 함수화, 즉 모듈화 하고 이를 순차적으로 불러오는 것을 말한다.<br>
예를 들어서 5라는 숫자 데이터를 18로 변형하기 위해선 이러한 방법을 활용할 수 있다.<br>

```
var a = 5;
const multiplyAndAdd3 = (number) => {
return number * 3 + 3
}

혹은 모듈화를 위해 각각의 함수를 정의하고 이를 실행할 수도 있을 것이다.

const multiply = (x) => x * 3;
const add3 = (x) => x + 3

위와 같이 정의할 경우 함수 호출 시

add3(multiply(5));

와 같이 호출 할 수 있다.

pipe는 이러한 과정에서 추가되는 연산, 즉 펑션들의 수가 많아질 때 아주 유용하게 사용할 수 있는 함수의 패턴이다.

pipe(multiply, add3)(5);

식이 길어진다면 pipe방법이 훨씬 가독성이 좋다.
ex)
const compose = (…fns) => data => fns.reduceRight((acc, funcs) => funcs(acc), data);
```

### Compose

compose는 파이프와 같으나 펑션이 반대의 순서, 오른쪽에서 왼쪽으로 실행되는 차이가 있다.

---

### Written

- 📜 [Currying in JavaScript ES6 — Adam Bene](https://medium.com/@acparas/what-i-learned-today-july-2-2017-ab9a46dbf85f)

### Video

Nothing
