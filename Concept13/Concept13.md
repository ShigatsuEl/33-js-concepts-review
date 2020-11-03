## DOM과 Layout Trees

이번 Concept은 DOM에 관한 이야기를 해보겠습니다.<br>

자바스크립트를 배우다보면 자주 보이는 것이 DOM이란 친구입니다.<br>
그에 관한 문서를 여러 개 읽어봤지만 DOM이 HTML과 비슷하단 느낌을 받았습니다.<br>
이 둘은 서로 비슷하지만 같지 않습니다.<br>

`DOM`은 Document Object Model의 줄임말로 HTML / XML 문서의 프로그래밍 인터페이스입니다.<br>
이게 무슨 말이냐..<br>
우리가 HTML을 만들게 되면 자기가 원하는대로 웹의 뼈대를 만들 수 있습니다.<br>
그러나 HTML을 가지고 프로그래밍을 할 수 있을까요?<br>
가능은 할지 몰라도 한정되어 있습니다.<br>

따라서 HTML을 스크립트 언어 또는 프로그래밍 언어(자바스크립트)를 사용하기 위해서는 `DOM`이라는 친구가 필요합니다.<br>
DOM은 HTML 문서를 토대로 구조화된 표현으로 만들어 프로그래밍 언어가 DOM을 통해 스타일, 내용 등을 프로그래밍 할 수 있게 도와줍니다.<br>

```
예를 들어 HTML이 있습니다.

<div id="container"></div>

우리는 프로그래밍 언어로 이것을 프로그래밍 할 수 있습니다.
<script>
  var container = document.getElementById("container");
  container.innerHTML = "New Content!";
</script>

HTML은 div 하나를 가지지만 DOM은 div의 innerHTML이 "NEW Content!"를 또한 가지고 있습니다.
```

이렇듯 서로 같아보이지만 이러한 관점으로 보면 조금 다르다는 것을 알 수 있습니다 :)<br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [What is the DOM? — Chris Coyier](https://css-tricks.com/dom/)

- 📜 [DOM 소개](https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/%EC%86%8C%EA%B0%9C)

### Video

Nothing
