## async/await

이번 Concept은 async/await에 대해서 알아보겠습니다.<br>

지난 Concept에서 우리는 Promise라는 것에 대해 알아보았습니다.<br>
프로미스는 자바스크립트가 비동기 처리를 할 수 있는 방식이라고 설명했었습니다.<br>
이렇게 비동기 처리 방식을 할 수 있는 또 다른 방법이 하나 더 있습니다.<br>

바로 async/await 입니다. :)<br>
async/await는 Promise의 업그레이드 버전으로 매우 간단하게 비동기 처리를 할 수 있습니다.<br>

async에 관하여 먼저 알아보겠습니다.<br>

```
async function f() {
  return 1;
}
async는 비동기라는 뜻을 가지며 다음과 같이 함수 앞에 배치할 수 있습니다.
함수 앞에 async를 선언하게 되면 return값으로 Promise를 반환하게 됩니다.
아래와 같이 말이죠!

async function f() {
  return Promise.resolve(1);
}

f().then(alert); // 1

위 식은 아래 식과 똑같이 작용합니다.

async function f() {
  return 1;
}

f().then(alert); // 1

Promise를 사용하지 않아도 async 한 단어로 간단하게 표현이 가능하며
식도 간결해졌습니다.
```

그렇다면 await는 무슨 역할을 할까요?<br>

```
// works only inside async functions
let value = await promise;

await는 자바스크립트에서 promise가 안정된 결과값을 반환할 때까지 기다려줍니다.
또한 await는 반드시 async 내에서만 작동한다는 점을 알아두셔야 합니다.
다음은 await를 알아 볼 수 있는 좋은 예제를 준비했습니다.

async function f() {

  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });

  let result = await promise; // wait until the promise resolves (*)

  alert(result); // "done!"
}

f();

promise가 resolve를 반환할 때까지 밑의 코드로 넘어가지 않고 기다리는 것 입니다.
만약 await를 지워버린다면 결과는 어떻게 될까요?
result는 undefined가 될 것 입니다.
```

---

### Written

- 📜 [async/await — JavaScript.Info](https://javascript.info/async-await)

### Video

Nothing
