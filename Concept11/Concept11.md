## 자바스크립트 엔진

이번 Concept은 자바스크립트 엔진을 다룹니다. 역사에 관한 이야기가 많을 듯 ㅠㅠ<br>

자바스크립트 엔진은 도대체 무엇이며 무슨 역할을 하는 것 일까요?<br>
대표적인 자바스크립트 엔진 중 하나인 `V8`은 크롬 그리고 엣지에서 사용되고 있습니다.<br>
'V8'은 자바스크립트 코드를 기계와 더 가까운 low-level(기계어) 코드로 바꿔주는 역할을 합니다.<br>
또한 이러한 엔진은 현재 `ECMAScript`라는 표준을 사용하고 있습니다.<br>

'V8'은 다음과 같은 특징을 가집니다<br>

1. V8 엔진은 C ++로 작성되었으며 Chrome 및 Nodejs에서 사용됩니다.
2. ECMAScript 표준을 따릅니다.
3. V8 엔진은 독립으로 실행할 수 있으며 자체 C ++ 프로그램에 임베드 할 수 있습니다.

또한 C++에서 자체 함수 구현을 추가하여 JavaScript에 새로운 기능을 추가 할 수 있기도 합니다.<br>
예를들어 NodeJS위에서 `print(hello)`같은 구문은 유효하지 않으며 컴파일하면 오류가 발생합니다.<br>
하지만 V8에서 C++로 print 기능을 추가하여 이것을 작동하게 할 수 있습니다.<br>
이를 통해 자바스크립트는 자바스크립트 표준(ECMAScript)보다 더 이해할 수 있게 된 것입니다.<br>

이는 C ++가 JavaScript에 비해 프로그래밍 언어로서 더 많은 기능을 가지고 있기 때문에 이렇게 작용하는 것입니다. 하드 드라이브의 파일 및 폴더를 처리하는 것과 같은 하드웨어에 훨씬 더 가깝기 때문입니다.<br>
따라서 C ++로 코드를 작성하고 JavaScript에서 사용할 수있게함으로써 JavaScript에 더 많은 기능을 추가 할 수 있습니다.<br>
유사하게, 우리는 V8 내부에 C ++의 다른 새로운 기능의 우리 자신의 구현을 추가하여 Node.js가 이해할 수 있도록 할 수도 있습니다.<br><br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [Understanding How the Chrome V8 Engine Translates JavaScript into Machine Code — DroidHead](https://www.freecodecamp.org/news/understanding-the-core-of-nodejs-the-powerful-chrome-v8-engine-79e7eb8af964/)

### Video

Nothing
