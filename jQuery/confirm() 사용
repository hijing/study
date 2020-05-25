# selectbox change시 confirm() 사용, 기존에 선택된 값으로 되돌리기

jquery, selectbox change시 confirm() 사용하였을 경우
confirm() --> No("취소") 선택 시 취소 했음에도 원래의 값으로 돌아오지 않음

그래서 최초 선택되어 있던 값으로 되돌리기(undo) 위해서 change() + focus() 이벤트를 사용하면 해결됨

```
$(document).ready(function(){
             
	var prev_val ;
	$('#cd').focus(function(){
	prev_val = $(this).val();
	}).change(function(){
	$(this).blur(); 
	if(confirm("입력된 값이 초기화 됩니다. 변경하시겠습니까?")){
	       // Todo
	           alert('changed');
	}else{
	       // 기존에 선택한 값으로 Undo
	       $(this).val(prev_val);
	           alert('unchanged');
	       return false;
	}
	});
});
```
