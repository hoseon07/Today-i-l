# 5. position & transition

## 함수란?

함수란, 특정한 기능을 가지고 있는 상자와 같은 것이다.

x+10이라는 기능을 가지고 있는 상자에 숫자를 넣으면 11이라는 숫자가 나오게 된다. 이렇게 지정된 기능을 수행하는 요소를 함수라고 함.

## calc()

`calc()`이라는 함수를 이용하면, 괄호 안의 사칙연산을 수행한 결과를 속성값으로 사용할 수 있다.

### 덧셈, 뺄셈

```
/item1{
	background: red;
	width: calc(50px + 50px);
	height: 50px;
}
.item2{
	background: blue;
	width: calc(100% - 120px);
	height: 50px;
}
```

> `calc()`함수 사용시 덧셈, 뺄셈 기호 앞 뒤에 반드시 공백을 줘야 함.
> 

### 곱셈, 나눗셈

```
.item3{
	background: green;
	width: calc(2*100px);
	height: 590px;
}
.item4{
	background: orange;
	width: calc(100%4);
	height: 50px;
}
```

# position

position이란 HTML 요소가 배치되는 방식을 결정하는 속성이다.

## position 속성값

포징션이라는 속성에는 총 다섯가지 속성값을 줄 수있다.

- static(기본값)
- relative
- absolute
- fixed
- sticky

position에 어떠한 속성값을 입력했느냐에 따라, 

**`top, left, bottom, right`**속성을 이용해 요소의 좌표값을 변경하는 방식이 달라짐

 

### position: static(기본값)

문서상 원래 있어야 하는 위치에 배치됨

❗`이때는 top, left, bottom, right 속성을 사용할 수 없다.`

즉, **위치 조정이 불가능한 기본 HTML 요소의 상태**라고 생각할 수 있다.

### position : relative

`**원래 있던 자리를 기준**`으로 **요소의 위치를 조정**할 수 있다.

top, left, bottom, right 속성 적용이 가능함.

### position : absolute

`**절대 좌표를 기준**`으로 **요소의 위치를 조정**할 수 있다.

기준이 절대 좌표인 만큼, **절대 좌표의 기준이 되는 축**이 있어야 하므로 대상 요소의 부모 중 `**relative가 적용된 요소**`를 찾아서 **절대 좌표의 기준**으로 삼게 된다.

만일, relative가 적용된 요소가 없다면, HTML의 body 전체를 기준으로 한다. top, left, bottom, right 속성 적용이 가능함.

### position : fixed

`**viewport를 기준**`으로 **요소의 위치를 조정**할 수 있다.

스크롤을 내려도 사라지지 않고 화면 어딘가에 고정되어 있는 것을 position : fixed를 이용해서 만듬.

top, left, bottom, right 속성 적용이 가능함.

### position : sticky

`**부모 요소의 좌표 기준**`으로 **요소의 위치를 조정**할 수 있다.

position : sticky는 최근에 추가된 속성이다.

**스크롤이 내려가지 않았을 때는 static처럼 작동**하다가, 해당요소의 위치 **아래로 스크롤이 내려가지 지정한 좌표에 고정**시켜 준다.

---

## Z-index

position을 이용해 요소의 위치를 옮기다보면 여러개이 요소가 겹치는 경우가 발생함. 그런 상황에서 우선 순위를 정해야 하는 경우에 사용할 수 있다.

### z축이란?

우리가 흔히 아는 2차원 공간을 `**3차원 공간으로 확장하게 되면 z축**`이 하나 더 생기게 된다.

```
z-index: auto (기본값)
z-index: 1
z-indexL: 9990
```

---

# transition

css에서 애니메이션을 줄 수 있는 방법에는 크게 두 가지가 있다.

`**transition**`은 CSS 속성을 이용한 변화의 전, 후 사이에 애니메이션을 추가해서 움직임을 부드럽게 만들어 줄 수 있다.

### transition-property

어떤 `**속성(property)에 transition을 적용할 것 인지**`를 지정함.

```
transition-property : color, transform
```

위의 코드는 color, transform처럼 property를 지정해 준것이다.

### transition-timing-function

`**transition의 속도 패턴**`을 지정함.

transition의 변화가 일정한 속도로 일어날 것인지, 아닌지 빠르게 시작했다가 느리게 끝날 것인지 같은 속도 패턴을 지정함.

```
transition-duration: ease-in-out | ease | ease-in | ease-out
```

- `ease-in-out`: 천천히 시작했다가, 정상 속도가 됐다가, 빠르게 끝남.
- `linear`: 일정한 속도로 변화함.
- `ease`: 시작할때는 빨라지다 느려짐.
- `ease-in`: 천천히 시작했다가 속도를 높여 끝난다.
- `ease-out`: 빠른 속도로 시작했다가, 천천히 끝남.

### transition-delay

`**transition 요청을 맏은 후 실제로 실행되기까지 기다려야 하는 시간의 양**`을 지정함.

```
transition-delay: 2s;
```

위의 코드는 전환효과(transition)가 시작되기까지 걸리는 시간을 지정함.

즉, 이벤트가 발생한 시점으로부터 2초 이후에 transition이 일어나게 됨

delay는 초(s), 혹은 밀리초(ms) 단위로 지정함.