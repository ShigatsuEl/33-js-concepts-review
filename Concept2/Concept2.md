## 원시 자료형(Primitive Values)

이번 Concept은 필수 개념도 맞지만 거의 기초에 가깝기 때문에 자세히 다루지는 않으려고 합니다.<br><br>

Primitive Valuse는 객체를 제외하고 변경될 수 없는 값을 정의합니다.<br><br>

1. Boolean Type
   
   Bool값은 True 아니면 False를 가집니다.

2. Null vs Undefined
   
   ```
   let x = null;
   // x는 정의는 되었지만 값이 존재하지 않음

   let y;
   console.log(y);

   result

   undefined
   // y는 정의되지 않았음
   // unll = 공익 / undefined = 미필이라 생각하면 편하다.
   // 이번 Concept에서는 null과 undefined의 차이만 알아가도 성공이다.
   ```

3. Number & BigInt

    Number는 말 그대로 숫자를 의미<br>
    타입을 지정해줘야 하는 다른 프로그래밍 언어와는 다르게 자바스크립트는 런타임으로 작동하므로 적용되는 값에 따라 타입이 바뀐다.<br>
    타입은 숫자외에 +Infinity, NaN, -Infinity가 있습니다.<br>

    BigInt는 자바스크립트에서 대표하는 정수 값을 초과했을 때 사용합니다.<br>
    정수 끝에 n을 추가하는 것으로 사용할 수 있습니다.<br>

4. String
   
   자바스크립트에서 String은 텍스트 데이터를 나타내는 데 사용됩니다.<br>
   중요한 점은 자바스크립트에서 String은 값을 변경할 수 없다는 것 입니다.<br>

5. Symbol
   
   Symbol은 최근 자바스크립트에서 나온 것으로 고유하고 변경 불가능한 값입니다.<br>

너무 기본적인 내용이라 리뷰하기가 힘드네용 ㅠㅠ<br>
더 자세한 내용을 원하시면 예전에 작성한 [Primitive Type](https://github.com/ShigatsuEl/dream-coding__javascript/blob/master/Chapter%2003/Chapter%2003.md)을 참고하십시오.

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [JavaScript data types and data structures - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Primitive_values)

### Video

Nothing