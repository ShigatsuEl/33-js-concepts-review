## map, reduce, filter

이번 Concept은 배열에서 사용되는 map & reduce & filter에 대해서 간략하게 설명하겠습니다. :)<br>

1. map

   map() 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환합니다.<br>

   ```
   const array1 = [1, 4, 9, 16];

   // pass a function to map
   const map1 = array1.map(x => x * 2);

   console.log(map1);
   // expected output: Array [2, 8, 18, 32]

   array1 배열에서 map메서드를 사용해 element(요소) 하나 하나마다
   곱하기 2를 해주는 콜백함수를 파라미터로 가집니다.
   결과는 새 element를 가지는 배열을 나타냅니다.
   ```

2. reduce

   reduce() 메서드는 배열의 각 요소에 대해 주어진 리듀서(reducer) 함수를 실행하고, 하나의 결과값을 반환합니다.<br>

   ```
   const array1 = [1, 2, 3, 4];
   const reducer = (accumulator, currentValue) => accumulator + currentValue;

   // 1 + 2 + 3 + 4
   console.log(array1.reduce(reducer));
   // expected output: 10

   // 5 + 1 + 2 + 3 + 4
   console.log(array1.reduce(reducer, 5));
   // expected output: 15

   reduce() 메서드는 하나의 콜백함수를 가지며
   이 콜백함수는 이전 값과 현재 값(배열 안의 요소)를 가지고 어떠한 작업을 합니다.
   예를 들어 위에서는 이전값과 현재값을 더하고 그 결과가 다시 이전값으로 들어갑니다.
   이것이 배열 안의 모든 요소들에 적용되어 다 더하면 10이라는 결과가 나오게 됩니다.
   즉, reduce() 메서드는 누적된 값을 구하고자 할 때 많이 사용됩니다.
   ```

3. filter

   filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환합니다.<br>

   ```
   const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

   const result = words.filter(word => word.length > 6);

   console.log(result);
   // expected output: Array ["exuberant", "destruction", "present"]

   위 예제에서 filter 메서드는 배열 안의 요소 길이가 6 초과인 경우만 해당해 새로운 배열을 만듭니다.
   ```

---

### Written

- 📜 [Array.prototype.map() — MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

- 📜 [Array.prototype.reduce() — MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

- 📜 [Array.prototype.filter() — MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

### Video

Nothing
