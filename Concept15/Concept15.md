## this, call, apply, bind

이 Concept은 this / call / apply / bind를 순차적으로 다뤄보겠습니다.<br>

1. this

   저는 `this`를 볼 때마다 너무 어려워했습니다.<br>
   도대체 이 this가 누굴 가리키는걸까? 코드가 길어지면 길어질수록 this가 누구인지 알아가는 것을 포기하고 감으로 때려 맞춰야 했습니다.<br>
   때문에 이번 컨셉에서 this를 처음보는 사람도 이해할 수 있게 확실하게 정리하려고 합니다.<br>

   this는 어려워보이지만 사실은 이것만 알고 있으면 됩니다!<br>
   `누가 호출했나요?`<br>
   호출을 누가했는지 잘 봐야합니다. 이것만 볼 줄 알면 this는 정말 간단하게 느껴질 것 입니다.<br>
   this는 크게 4가지 경우로 사용되는데 4가지 경우를 전부 다뤄보겠습니다.<br>

   1. 일반 함수 실행 방식

      ```
      function foo () {
      console.log(this);
      }

      foo();

      // 일반 함수 실행 방식을 먼저 보겠습니다.
      여기서 누가 this를 호출했나요??
      바로 window입니다.

      아니 어떻게 window가 될 수 있나요?
      사실 위의 코드는 이렇게 되어 있는 것 입니다.

      function foo () {
      console.log(this);
      }

      (window).foo();

      보이시나요?
      사실은 window가 생략되어 있기 때문에 보이지 않는 것일 뿐
      window가 foo()함수의 this를 부르고 있었던 겁니다.
      이해가 가신다면 다음 예제를 보겠습니다.
      ```

      ```
      let age = 100;

      function foo () {
        let age = 99;
        bar(age)
      }

      function bar () {
        console.log(this.age);
      }

      foo();

      // 위와 같은 경우는 어떨까요?
      일단 맨 밑에서 (window).foo()가 먼저 호출되었고
      foo()함수에서 bar(age)가 호출 되었습니다.

      // 이 경우에 this를 부른 친구는 bar(age)입니다.
      정확하게는 (window).bar(age)가 this를 부른 것 이죠!
      그렇기 때문에 foo()함수의 age가 출력될 것 같으면서도
      콘솔로그에서는 99가 아닌 100이 출력 되는 것 입니다.
      ```

   2. 도트 표기법

      다음으로는 도트가 호출하는 경우를 보겠습니다.

      ```
      let age = 100;

      let ken = {
        age: 35,
        foo: function () {
        console.log(this.age); // 35
        }
      }

      ken.foo();

      // 이 경우는 일반 함수 호출과 다릅니다.
      여기서는 누가 this를 호출했나요?
      window가 호출하지 않았습니다.
      마지막 줄 코드 ken.foo()에서 ken이 호출한 것을 알 수 있습니다.
      따라서 age값은 100이 아니라 ken의 나이인 35가 출력됩니다.

      // 일반 함수 호출과 도트 표기법의 공통점을 알 수 있습니다.
      누가 호출했는지 보려면 .(점) 앞에 누가 있는지를 보면 알 수 있다는 것이죠
      아래에서 예제를 하나 더 보겠습니다.
      ```

      ```
      function foo() {
        console.log(this.age);
      }

      let age = 100;

      let ken = {
        age: 36,
        foo: foo
      }
      let wan = {
        age: 32,
        foo: foo
      }

      ken.foo(); // 36
      wan.foo(); // 32

      let fn = ken.foo;
      fn(); // 100

      // 위에서 개념이 이해되었다면 이제 이 예제도 쉽게 이해가 갈 것 입니다.
      foo()함수에서 this는 밑의 코드에서 각각 다른 방법으로 호출되었기 때문에
      ken.foo()는 this가 ken을 가리키므로 36
      wan.foo()는 this가 wan을 가리키므로 32
      그리고 변수 fn은 ken 객체의 foo함수를 할당했지만 (window).fn()으로
      호출 했기 때문에 age는 100이 출력되게 됩니다.
      ```

   3. 명백한 바인딩 / call & bind & apply

      this의 개념을 알았다면 call & bind & apply 개념을 이해하는 것도 간단하다.<br>
      this는 앞에서 보았듯이 호출하는 상대가 누군지에 따라 가리키는 친구가 달라집니다.<br>
      하지만 call & bind & apply는 이것을 무시하고 가리키고 싶은 상대를 확실하게 가리키는 역할을 합니다.<br>
      그리고 call & bind & apply는 함수의 Web API 메서드 입니다.<br>

      1. call

         ```
         let age = 100;

         function foo() {
           console.log(this.age);
         }

         let ken = {
           age: 35,
           log: foo
         }

         foo.call(ken, 1, 2, 3);

         // 보는 것과 같이 foo()함수는 call 메서드를 사용함에 따라
         이제 누가 불렀냐는 상관없이 call메서드라 첫 번째 인자로 지정한
         ken객체를 가리키게 됩니다.
         뒤에 있는 나머지 인자들은 함수에 대한 인수로 1, 2, 3은 foo()함수가
         아무런 파라미터도 갖지 않기 때문에 무시됩니다.

         조금 더 어려운 예제를 보겠습니다.
         ```

         ```
         function Product(name, price) {
           this.name = name;
           this.price = price;
         }

         function Food(name, price) {
           Product.call(this, name, price);
           this.category = 'food';
         }

         function Toy(name, price) {
           Product.call(this, name, price);
           this.category = 'toy';
         }

         const cheese = new Food('feta', 5);
         const fun = new Toy('robot', 40);

         // Product.call에서 바인딩으로 this를 지정했습니다.
         그렇다면 Food함수의 this는 누가 호출했을까요?
         맨 밑에 두 코드에서 cheese와 fun이라는 변수가 호출했습니다.
         정확하게는 새 객체가 생성되고 cheese와 fun에 할당된 변수입니다.
         ```

      2. bind

         call & apply와 bind의 차이점은 전자는 호출은 하지만 후자는 호출하지 않습니다.

         ```
         var obj = {
           string: 'zero',
           yell: function() {
             alert(this.string);
           }
         };

         var obj2 = {
           string: 'what?'
         };

         var yell2 = obj.yell.bind(obj2);
         yell2(); // 'what?'

         // 보는 바와 같이 obj.yell의 함수의 this는 obj2 객체를 가리키게 bind해줬습니다.
         yell()로 호출해줘야 what이 출력되게 되는 것 입니다.
         즉, call(this, 1, 2, 3)은 bind(this)(1, 2, 3)과 같습니다.
         ```

      3. apply

         ```
         let age = 100;

         function foo() {
           console.log(this.age);
         }

         let ken = {
           age: 35,
           log: foo
         }

         foo.apply(ken, [1, 2, 3]);

         // apply는 call과 조금 다릅니다.
         단지 배열을 인자로 넣을 수 있습니다.
         ```

   4. new 키워드를 사용한 함수 실행

      코드를 보면서 설명하겠습니다.

      ```
      function Foo () {
        console.log(this.age); // undefined
        this.age = 100; // 빈 객체에 속성 추가
        console.log(this.age); // 100
      }

      new Foo();

      // 아주 좋은 예제입니다.
      new 생성자는 Foo()함수를 통해 하나의 새로운 빈 객체를 생성합니다.
      이 빈 객체가 this를 호출하며 this가 빈 객체를 가리키게 됩니다.
      또한 첫 번째 콘솔로그로 나이를 찍어보면 undefined가 출력됩니다.
      빈 객체이기 때문이죠
      하지만 이 빈 객체에 age = 100을 입력해주고
      두번째로 콘솔로그 찍어보면 100이라는 값이 나오게 됩니다.

      다음 예제로 갑시다.
      ```

      ```
      function Person () {
        this.name = 'ken';
        console.log(this);
      }

      var ken = new Person();
      console.log(ken);
      여기에서는 this가 ken이라는 변수가 호출하며
      ken은 새로운 객체가 할당됩니다.
      ```

이번 컨셉은 상당히 길게 다뤄봤습니다.<br>
제가 this에 대해서 취약하여 다시는 헷갈리지 않게 예제를 많이 넣어봤습니다 :)

---

### Written

- 📜 [자바스크립트, this의 4가지 역할](https://im-developer.tistory.com/96)

- 📜 [call() — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)

- 📜 [bind() — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)

- 📜 [apple() — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

### Video

Nothing
