## 재귀

이번 Concept은 재귀에 관한 이야기 입니다.<br>
아직 33번째 컨셉까지 다 다루려면 멀었긴 했지만 이번 컨셉은 제가 생각하기에 엄청나게 중요한 것 같지는 않습니다.<br>
일단은 간단하게 개념만 남겨놓고 나중에 놓쳤다고 생각되면 다시 돌아와서 수정하겠습니다.<br>

재귀는 단순히 함수가 자기 자신을 호출하는 것을 말합니다.<br>

```
function factorial (x) {
  if (x <0) return;
  if (x === 0) return 1;
  return x * factorial (x-1);
}
계승 (3);
// 6

이것은 사실 팩토리얼을 만든 함수입니다.
return 에 자기 자신을 호출하여 계속해서 실행될 것 입니다.
종료 조건 | 기본 케이스 등 이런 개념은 다루지 않겠습니다.
```

그냥 아 그렇구나 하고 넘어가면 될 것 같습니다. :)<br>
글 쓰기도 애매했는데 필수 개념 33가지에 포함되어 있어 일단은 올려봅니다.<br>

---

### Written

- 📜 [Learn and Understand Recursion in JavaScript — Brandon Morelli](https://codeburst.io/learn-and-understand-recursion-in-javascript-b588218e87ea)

### Video

Nothing
