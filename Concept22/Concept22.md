## 고차함수

이번 Concept은 고차함수에 관해 간략히 이야기 해보겠습니다.<br>

고차함수라고 해서 상당히 어려운 개념일 줄 알았는데 알고보니 내가 평상시에 무심코 쓰는 것이었다.<br>

```
const characters = [
  {name: 'Han Solo'},
  {name: 'Luke SkyWalker'},
  {name: 'Leia Organa'}
];

먼저 객체 배열이 있습니다.
이제 여기에 map()메서드를 사용해 콘솔에 로그해보겠습니다.
```

```
// ES6 syntax
const names = characters.map(character => character.name);
console.log(names); // "Han Solo" "Luke SkyWalker" "Leia Organa"

// ES5 syntax
var names2 = characters.map(function(character) {
  return character.name;
});

console.log(names2); // "Han Solo" "Luke SkyWalker" "Leia Organa"

map 메소드가 다른 함수를 매개 변수로 사용하는 `콜백 함수`
이것이 고차함수와 비슷하다고 할 수 있습니다.
바로 함수 파라미터로 함수를 넣고 이 과정을 반복하는 것
```

고차함수를 사용하면 복잡한 작업을 할 수 있습니다.<br>
하지만 너무 남용하면 코드를 읽기가 힘들며 유지보수도 어렵습니다.<br>

---

### Written

- 📜 [Higher Order Functions in JavaScript — John Hannah](https://www.lullabot.com/articles/higher-order-functions-in-javascript)

### Video

Nothing
