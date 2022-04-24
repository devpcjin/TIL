# 키보드 활성화 여부 체크

## HTML
``` html
<input type="password" class="form-control" placeholder="Password" id="pw" onkeyup="checkCapsLock(event)">
<div id='message' class="capslock-check"></div>
```
- ```onkeyup = "checkCapsLock(event)"```
    - `onkeyup` : 키보드를 눌렀다 떼는 순간
    - `checkCapsLock(event)` 함수 호출

## Javascript
``` js
    function checkCapsLock(event) {
        if (event.getModifierState("CapsLock")) {
            document.getElementById("message").innerText
                = "Caps Lock이 켜져 있습니다."
        } else {
            document.getElementById("message").innerText
                = ""
        }
    }
```

- `event.getModifierState("CapsLock")`
    - CapsLock의 활성화 여부 출력 (활성 : true, 비활성 : false)


## KeyboardEvent.getModifierState()
- CapsLock
- NumLock
- ScrollLock
- Alt
- Shift
- Ctrl

[더 많은 키보드 기능 참고 링크](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState)

