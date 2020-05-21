# input type이 number일 때 입력 글자 수 제한하기

input type이 text일 때는 maxlength의 값만 주면 간단하게 해결 되지만

input type이 number 일 때는 maxlength가 정상 작동하지 않는다.

이럴 때는 input 속성의 oninput과 간단한 스크립트를 활용해서 해결 할 수 있다.


※ 예제) 생년월일을 입력하는 필드에 6자리로 입력 글자 수 제한하기

1. HTML
```
<input class="form-control" type="number" placeholder="생년월일 6자리 ex)910504" 
maxlength="6" oninput="numberMaxLength(this);"
```

2. Script
```
<script>
    function numberMaxLength(e){
        if(e.value.length > e.maxLength){
            e.value = e.value.slice(0, e.maxLength);
        }
    }
</script>
```
