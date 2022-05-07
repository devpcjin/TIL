# Class Handler

## addClass(className)
- 해당 className을 가진 클래스 속성을 추가
- 이벤트가 발생한 노드에 선언된 클래스 스타일을 적용

## removeClass(className)
- 해당클래스 속성을 지정된 노드에서 제거

## hasClass(className)
- 선택한 요소에 클래스가 있는지 확인

## toggleClass(className)
- 스타일 클래스가 적용된 경우는 제거를, 속성이 선언되어 있지 않은 경우에는 선언
    ```js
        function toggle_sign_up() {
            $("#sign-up-box").toggleClass("is-hidden")
            $("#div-sign-in-or-up").toggleClass("is-hidden")
            $("#btn-check-dup").toggleClass("is-hidden")
            $("#help-id").toggleClass("is-hidden")
            $("#help-password").toggleClass("is-hidden")
            $("#help-password2").toggleClass("is-hidden")
        }
    ```
  - `is-hidden`은 bulma class 임 [docs](https://bulma.dev/classes/helpers/is-hidden)
