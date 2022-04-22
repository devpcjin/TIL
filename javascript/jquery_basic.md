# JQuery
## JQuery란?

> jQuery(제이쿼리)는 HTML의 클라이언트 사이드 조작을 단순화 하도록 설계된 크로스 플랫폼의 자바스크립트 라이브러리다.
> -<cite>[wikipedia][1]</cite>

[1]: https://ko.wikipedia.org/wiki/JQuery

## JQuery와 Javascript

> 👉 jQuery는 Javascript와 다른 특별한 소프트웨어가 아니라 미리 작성된 Javascript 코드입니다.
> Javascript로 길고 복잡하게 써야 하는 것을
>   ```jsx
>    document.getElementById("element").style.display = "none";
>    ```
>   jQuery로 보다 직관적으로 쓸 수 있어요.
>   ```jsx
>   $('#element').hide();
>    ```
>  

## import 하기
- 미리 작성된 Javascript 코드를 가져오는 것
- [jQuery CDN](https://www.w3schools.com/jquery/jquery_get_started.asp) 추가하기

>   ```<head>``` 와 ```</head>``` 사이에 아래 문장 추가해서 import
>   ``` html
>   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
>   ```

## 자주쓰는 JQuery

### div 보이기 /  숨기기
```javascript
// 크롬 개발자도구 콘솔창에 쳐보기
// id 값이 post-box인 곳을 가리키고, hide()로 안보이게 한다.(=css의 display 값을 none으로 바꾼다)
$('#post-box').hide();

// show()로 보이게 한다.(=css의 display 값을 block으로 바꾼다)
$('#post-box').show();
```

### CSS의 값 가져오기
``` jsx
$('#post-box').hide();
$('#post-box').css('display');

$('#post-box').show();
$('#post-box').css('display');
```

### 태그 내 텍스트 입력하기
- **input box의 경우**
  ``` jsx
  $('#post-url').val('여기에 텍스트를 입력하세요.');
  ```
- **다른 것들** _
ex) 버튼의 텍스트 바꾸기_
  ``` jsx
  // 가리키고 싶은 버튼에 id 값을 준다음
  <button id="btn-posting-box" type="button" class="btn btn-primary">포스팅 박스 열기</button>
  ``` 
  ``` jsx
  $('#btn-posting-box').text('포스팅 박스 닫기');
  ```
  