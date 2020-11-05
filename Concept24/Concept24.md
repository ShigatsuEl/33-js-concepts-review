## 컬렉션과 생성기

이번 Concept은 컬렉션에 관해서 조금 다뤄보고 넘어가겠습니다.<br>

컬렉션은 데이터 구조 입니다.<br>
데이터를 어떻게 저장할 지에 관한 방법이라고 일단은 표현해보겠습니다.<br>

이미 Object와 Array로 데이터를 저장할 수 있지만 이것 만으로는 충분하지 않습니다.<br>
`Map`과 `Set`이 탄생하게 된 이유이기도 합니다.<br>

1. Map

   Map은 Object와 상당히 비슷한 형태를 가집니다.<br>
   Object와 Map은 둘 다 key와 value를 가지는데 Object와 Map의 차이점은 Object는 키가 String으로 구성되어 있고 반대로 Map은 키가 문자열 외에도 가능하다는 점 입니다.<br>

   ```
   예를 들면

   let map = new Map();

   map.set('1', 'str1');   // a string key
   map.set(1, 'num1');     // a numeric key
   map.set(true, 'bool1'); // a boolean key

   // remember the regular Object? it would convert keys to string
   // Map keeps the type, so these two are different:
   alert( map.get(1)   ); // 'num1'
   alert( map.get('1') ); // 'str1'

   alert( map.size ); // 3

   보다시피 1과 '1'의 value는 다릅니다.
   다른 key로 인정이 되는 것 입니다.
   ```

   Map의 자세한 기능은 다루지 않겠습니다. 이러한 개념이 있다는 것만 알면 됩니다.<br>

2. Set

   Set은 value 집합으로 키가 없습니다. 또한 각 값은 한 번만 발생할 수 있습니다.<br>

   ```
   let set = new Set();

   let john = { name: "John" };
   let pete = { name: "Pete" };
   let mary = { name: "Mary" };

   // visits, some users come multiple times
   set.add(john);
   set.add(pete);
   set.add(mary);
   set.add(john);
   set.add(mary);

   // set keeps only unique values
   alert( set.size ); // 3

   for (let user of set) {
     alert(user.name); // John (then Pete and Mary)
   }
   ```

즉 Map은 키 값 모음이며 Set은 고유한 값 모음입니다.<br>
더 자세한 내용을 알고 싶다면 밑의 링크를 참고하시길 바랍니다.

---

### Written

- 📜 [Map, Set, WeakMap and WeakSet — JavaScript.Info](https://javascript.info/map-set)

### Video

Nothing
