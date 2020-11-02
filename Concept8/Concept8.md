## IIFE, Modules, Namespaces

이번 Concept은 IIFE 그리고 Modules까지만 다뤄볼 생각입니다.<br>

IIFE(Immediately Invoked Function Expression)<br>

말 그대로 즉시 실행되는 함수 표현식입니다.<br>
쉽게 표현하면 코드가 시작하자마자 바로 실행되는 그런 함수인데요. 사용방법은 아래와 같습니다 :)<br>

```
(const func = () => {
  return "IIFE";
})()
```
뭔가 이상한 방법이지만 이것을 사용하면 아무도 이 함수를 바꿀 수 없게 된다고 합니다.<br>
브라우저는 실행하여 콘솔로그를 확인해보면 IIFE가 나오지만 누군가 func를 수정하려고 하면 func is not defined가 뜰 것 입니다.<br>

어차피 많이 사용되지 않습니다.<br>
그냥 이런 것이 있구나 하고 넘어가심 댈 듯 합니다 ㅎㅎ;;<br><br>

다음은 Modules입니다.<br>

모듈은 저도 정확하게 어떤 것인지 모르나 그냥 쉽게 생각하면 파일입니다.<br>
예를 들어 Webpack과 같은 모듈 번들러를 사용하면 import export 등과 같이 하나의 파일을 다른 파일에서 사용하는 것이 가능합니다.<br>
하지만 모듈 번들러가 없다면?<br>
import export를 사용해도 브라우저가 이게 무엇인지 인식하지 못합니다.<br>

만약 모듈 번들러를 사용하지 않고 브라우저를 이해시키려면 어떻게 해야할까요?<br>
아래에서 설명 해보겠습니다.<br>
```
<script src="app.js", type="module">
<script src="app2.js", type="module">
```
이렇게 `type="module"`을 해주는 것으로 모듈 번들러 없이 브라우저를 이해시키는 것이 가능합니다.<br>

이번 Concept은 여기서 마무리 입니다 ㅠ.ㅠ<br>

필자가 모듈에 대해 정확히 알지 못해 자세한 설명을 해드릴 수가 없네요.<br>
시간이 지나서 추가가 필요한 부분은 차차 업데이트 해나가겠습니다 :)

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

Nothing

### Video

- 🎥 [(EP 08.) 웹팩 없는 자바스크립트 모듈? | 자바스크립트 개발자라면 알아야하는 핵심 컨셉 33개](https://www.youtube.com/watch?v=WHAfp-1JPMg&list=PL7jH19IHhOLMmmjrwCi7-dMFVdoU0hhgF&index=3)

