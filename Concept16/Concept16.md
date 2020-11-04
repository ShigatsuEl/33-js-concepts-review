## new, 생성자, instanceof, 인스턴스

이번 Concept에서는 생성자와 인스턴스에 대해서 다뤄보겠습니다.<br>

### new 생성자

new 생성자는 객체를 만들어 낼 때 사용됩니다.<br>
지난 컨셉을 다루면서 객체를 만드는 두 가지 방법이 있었습니다.<br>
Factory Function에서 틀을 만들거나 class를 통해 틀을 만들어 내는 것 입니다.<br>

틀을 만들었으면 이제 찍어내는 일만 남았죠?<br>
틀을 통해 객체를 실제로 생성하려면 어떻게 해야하는지 기억하시나요?<br>
new 생성자를 사용하는 것 입니다.

```
// 틀
function Student(name, age) {
  this.name = name;
  this.age = age;
}

// 객체 생성
const student1 = new Student("홍길동", 20);
```

이것이 new 생성자 입니다.<br>

지난 컨셉을 하면서 많이 다뤘던 내용이라 많이 쉬워진 감이 있는 듯 합니다 ㅎㅎ..<br>

### typeOf vs instanceOf

이것도 [지난 컨셉5](https://github.com/ShigatsuEl/33-js-concepts-review/blob/master/Concept5/Concept5.md)를 통해 다뤘던 내용입니다.<br>
간단하게 집고 넘어가겠습니다.<br>

typeOf는 primitive value의 타입을 알고자 할 때 사용합니다.<br>
instanceOf는 객체 / 함수 / 배열과 같은 reference type의 타입을 알고자 할 때 사용합니다.<br>

---

### Written

- 📜 [JavaScript For Beginners: the 'new' operator — Brandon Morelli](https://codeburst.io/javascript-for-beginners-the-new-operator-cee35beb669e)

### Video

Nothing
