## Object.create와 Object.assign

이번 Concept은 Object.create와 Object.assign에 대해서 간단하게 알아보겠습니다 :)<br>

1. Object.create

   Object.create 메서드는 기존 개체를 새로 만든 개체의 프로토 타입으로 사용하여 새 개체를 만듭니다.<br>
   위를 MDN사이트에서 정의한 것 입니다.<br>
   잘 이해가 가지 않을 것 같아 풀어서 설명해보겠습니다.<br>

   ```
   const person = {
     isHuman: false,
     prin
       console.log(`My name is ${this.name}. Am I human? ${this.isHuman}`);
     }
   };

   const me = Object.create(person);

   me.name = 'Matthew'; // "name" is a property set on "me", but not on "person"
   me.isHuman = true; // inherited properties can be overwritten

   me.printIntroduction();
   // expected output: "My name is Matthew. Am I human? true"
   tIntroduction: function() {

   위의 코드에서 person이라는 기존 객체가 하나 있습니다.
   지난 컨셉에서 다뤘듯이 person은 __proto__라는 속성을 가지며
   여기서는 Object함수(Web API)를 가리킬 것 입니다.

   Object.create는 객체끼리 서로 참조하는 것이 아닌 새 객체를 만드는
   또 다른 방법 중 하나 입니다.
   단지 Object.create는 어떤 것을 프로토타입으로 복사할 것 인지에 대한
   하나의 파라미터를 받습니다.
   위의 예제에서 const me = Object.create(person)은
   me라는 객체를 새로 만들고 me 객체의 __proto__속성은
   바로 person객체를 가리킵니다.
   이로서 me -> person -> Object라는 proto chain이 형성되었습니다.
   ```

2. Object.assign

   Object.assign()메서드 는 하나 이상의 소스 개체 에서 대상 개체로 열거 가능한 모든 속성 을 복사 합니다 . 대상 개체를 반환합니다.<br>
   위에서 Object.create가 이해가 가셨다면 assing은 매우 쉽습니다.

   ```
   const target = { a: 1, b: 2 };
   const source = { b: 4, c: 5 };

   const returnedTarget = Object.assign(target, source);

   console.log(target);
   // expected output: Object { a: 1, b: 4, c: 5 }

   console.log(returnedTarget);
   // expected output: Object { a: 1, b: 4, c: 5 }

   Object.assign은 source 개체의 모든 속성을 target속성에 뒤짚어 씌우고 target객체를 반환합니다.
   따라서 결과는 { a: 1, b: 4, c: 5 }라는 결과가 나옵니다.
   ```

---

### Written

- 📜 [Object.create() — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)

- 📜 [Object.assign() — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)

### Video

Nothing
