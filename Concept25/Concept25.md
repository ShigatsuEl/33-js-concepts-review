## Promise

이번 Concpet은 비동기 방식 Promise에 관하여 다루고 있습니다. :)<br>

프로미스는 자바스크립트에서 비동기를 간편하게 처리해주는 오브젝트입니다.<br>
프로미스는 정해진 임무를 수행하고 나서 정상적으로 기능이 수행되었다면 성공의 메시지와 함께 처리된 결과값을 전달해줍니다.<br>
만약 임무를 수행하다 정상적으로 수행되지 못하면 에러를 발생시킵니다.<br>

![Concept25-1](./Concept25-1.png)<br>

위 사진은 Promise 동작 과정을 잘 표현하고 있습니다.<br>

Promise는 어떤 행동의 상태를 가집니다.<br>
예를 들어 공부를 다 끝냈는지 안 끝냈는지 확인하는 Promise가 있습니다.<br>
이 Promise는 3가지 상태를 가질 수 있습니다.<br>
`공부를 하는 중이다.`<br>
`공부를 마쳤다.`<br>
`공부를 하는지 모르겠다.`<br>

위는 각각 `pending` `fulfill` `reject` 3가지 상태를 반환합니다.<br>

이 Promise에서 return한 상태를 가지고 우리는 각각 다른 조치를 취할 수 있습니다.<br>
`then`<br>
`catch`<br>
`finally`<br>

then은 promise가 정상적으로 잘 수행이 되었다면 발생하는 메서드로 공부가 끝나면 상을 주는 메서드를 만들어 볼 수도 있습니다.<br>
catch는 promise가 중간에 정상적으로 동작이 되지 않거나 네트워크에 문제가 생겨 promise값을 받아올 수 없는 경우 생깁니다.<br>
finally는 promise 상태를 상관하지 않고 무조건 마지막으로 실행되는 메서드입니다.<br>

여기까지 Promise에 관해 초간단하게 다루어 보았습니다.<br>
이 Concept은 다른 레포지토리에서 다루었으므로 더 자세한 내용이 궁금하시다면 아래 링크를 참고하시길 바랍니다 :)<br>
[dream-coding\_\_js](https://github.com/ShigatsuEl/dream-coding__javascript/blob/master/Chapter%2012/Chapter%2012.md)

---

### Written

- 📜 [Promise — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### Video

Nothing
