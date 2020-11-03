## setTimeout, setInterval, requestAnimationFrame

이번 Concept에서는 setTimeout & setInterval & requestAnimationFrame에 대해 다뤄보겠습니다 :)<br>

1. setTimeout

   먼저 setTimeout은 저번 Concept에서도 다뤘다시피 단순한 함수가 아닌 Web API입니다.<br>
   setTimeout은 두 개의 인자를 가지며 첫 번째는 콜백함수 두 번째는 시간을 가집니다.<br>
   콜백함수는 바로 실행되지 않으며 메시지 큐로 옮겨진 후 콜스택이 비워진 후에 실행될 것 입니다.<br>
   중요한 것은 setTimeout이 가지는 `두 번째 파라미터는 지정된 시간 후에 실행되는 것이 아닌 메시지 큐에 쌓이게 되는 최소 시간을 의미합니다.`<br>
   이 말은 즉슨 5000으로 설정해도 5초 후에 실행되는 것이 아니라 5초 후에 메시지 큐에 쌓이게 되고 그 후에도 자바스크립트가 여유가 있으면 콜스택으로 불러오지만 그렇지 않으면 또 기다려야 한다는 것 입니다.<br>

   setTimeout을 사용하는 방법은 간단합니다.<br>

   ```
   const out = () => {
     console.log("hi");
   }

   const time = setTimeout(out, 5000);
   ```

   이렇게 하면 hi가 5초마다 출력되는 것을 확인하실 수 있습니다.<br>
   만약 타임아웃을 없애고 싶다면 clearTimeout을 사용해 이것을 삭제할 수 있습니다.<br>

2. setInterval

   setInterval은 setTimeout과 비슷하지만 지정된 시간마다 함수를 계속해서 호출해준다는 점이 있습니다.<br>

   ```
   const hi = setInterval(console.log, 1000, "hi");
   ```

   이렇게 코드를 작성하면 1초마다 콘솔로그에서 hi가 출력되는 것을 확인할 수 있습니다.<br>
   그런데 만약에 예를들어 1초보다 적게 1000/60으로 시간을 설정하게 된다면 어떻게 될까요?<br>
   크롬에서는 이것을 1초로 바꾸어 실행하게 됩니다.<br>
   그렇다면 1초보다 작고 빠르게 실행할 수 있는 방법은 없는 것 일까요?<br>

3. requestAnimationFrame

   위의 문제를 해결하고자 나온 것이 requestAnimationFrame입니다.<br>
   setInterval 같은 경우에는 위에서 말했다시피 1초마다 실행을 하는 것이 아니라 메시지 큐에 올라가서 대기하기 때문에 정확하게 1초단위로 실행되지 않을 수도 있습니다.<br>
   requestAnimationFrame은 이미지를 굉장히 빠르게 렌더링하는 작업을 합니다.<br>

   ```
   const animation = () => {
     console.log("animation");
     requestAnimationFrame(animation);
   }

   requestAnimationFrame(animation);
   // 매우 빠르게 animation이 출력될 것 입니다.
   ```

   이것은 웹을 인터랙티브하게 만들 때 많이 사용될 수 있는데 애니메이션처럼 초당 여러 번의 그림을 칠하게 되는 것이죠<br>
   따라서 이것은 cpu나 그래픽카드에 많은 의존을 하게 됩니다.<br>

이번 Concept은 여기서 마무리 하겠습니다 :)<br>

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [Using requestAnimationFrame — Chris Coyier](https://css-tricks.com/using-requestanimationframe/)

### Video

Nothing
