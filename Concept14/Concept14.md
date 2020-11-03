## 팩토리와 클래스

이번 Concept은 자바스크립트를 사용하면 누구나 한 번씩은 사용해본 경험이 있는 팩토리와 클래스에 대해 다뤄보겠습니다. :)<br>

Factory Function은 무엇일까요?<br>
말 그대로 객체를 만들어내는 공장 같은 느낌인데요<br>
객체를 여러 개 만들어 내야 한다고 가정해봅시다.<br>

```
여기에 원이라는 객체를 만들어 보겠습니다.

const circle = {
  radius: 1,
  location: {
    x: 1,
    y: 1
  },
  isVisible: true,
  draw: function() {
    console.log('draw');
  }
}

이렇게 circle이라는 객체를 하나 만들어 냈습니다.
circle을 하나 더 만들어 볼까요?

const circle2 = {
  radius: 2,
  location: {
    x: 2,
    y: 2
  },
  isVisible: true,
  draw: function() {
    console.log('draw');
  }
}

오.. 벌써부터 복붙하기 너무 귀찮군요 ㅋ.ㅋ
그렇다면 이번엔 공을 1000개를 찍어봅시다.
코드가 어떻게 될까요?
작성해보지 않아도 매우 헤비해진다는 것을 알 수 있습니다.
```

<br>
보는 것과 같이 객체를 여러 개 만들어 내야 한다면 많이 골치 아파질 수 있습니다.<br>
여기서 Factory Function이라는 개념이 등장합니다.
앞에서 말씀드렸다시피 객체를 만들어내는 공장함수라고 생각하시면 될 것 같습니다.<br><br>

```
// Factory Function
function createCircle(radius, locationX, locationY) {
  return {
    radius,
    locationX,
    locationY,
    draw() {
      console.log('draw');
    }
  };
}

Factory Function을 만들었습니다.
여기서 원을 2개 만들어볼까요?

const circle = createCircle(1, 1, 1);
const circle2 = createCircle(2, 2, 2);

짜잔!
함수를 하나 만든 것으로 객체를 단 1줄로 만들 수 있게 되었습니다.
```

이게 Factory Function이 필요한 이유입니다 :)<br>

그 후 ES6보다 더 위에 있는 모던한 자바스크립트 표준이 나오면서 최근에는 Class라는 것이 생겼는데 이는 Factory Function과 매우 비슷한 역할을 합니다.<br>

```
class Circle {
  constructor(radius, locationX, locationY) {
    this.radius = radius;
    this.locationX = locationX;
    this.locationY = locationY;
  }

  draw() {
    console.log('draw');
  }
}

const circle = new Circle(1, 1, 1);
const circle1 = new Circle(2, 2, 2);

이것이 최근에 나온 자바스크립트 클래스이며 더 이상 Factory Function을
만들지 않아도 되며 더 간편하게 객체를 찍어낼 수 있습니다.
```

클래스를 사용하면 유용한 웹 api를 더 활용할 수 있습니다.<br>
예를 들어 get & set과 같은...<br>

이번 MD에서는 이 내용에 관해선 다루지 않겠습니다.<br>
더 자세한 것이 알고 싶다면 -> [dream-coding\_\_js](https://github.com/ShigatsuEl/dream-coding__javascript/blob/master/Chapter%2006/Chapter%2006.md)를 활용하시길 바랍니다 :)

---

이 MD는 밑의 글과 영상을 참고하여 만들었습니다 :)

### Written

- 📜 [Class vs Factory function: exploring the way forward — Cristi Salcescu](https://www.freecodecamp.org/news/class-vs-factory-function-exploring-the-way-forward-73258b6a8d15/)

### Video

- 🎥 [JavaScript Factory Functions — Programming with Mosh](https://www.youtube.com/watch?v=jpegXpQpb3o)
