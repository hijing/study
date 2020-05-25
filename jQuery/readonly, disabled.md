# input 쓰기, 읽기, 활성화, 비활성화

```
<!DOCTYPE>
<html>
<head>
<title> 쓰기전용, 읽기전용, 활성화, 비활성화 </title>
</head>
<body>
<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
<input type="text" name="test" id="test"/><br>
<input type="button" id="readonly_t" value="읽기전용" />
<input type="button" id="readonly_f" value="쓰기전용" />
<input type="button" id="disabled_t" value="활성화" />
<input type="button" id="disabled_f" value="비활성화" />
<script type="text/javascript">
$(document).ready(function() {
	$("#readonly_t").click(function(){
		$("#test").attr("readonly",true).attr("disabled",false); //입력불가
	});
	
	$("#readonly_f").click(function(){
		$("#test").attr("readonly",false).attr("disabled",false); //입력가능
	});
$("#disabled_t").click(function(){
		$("#test").attr("disabled",false).attr("readonly",false); //입력가능
	});
$("#disabled_f").click(function(){
		$("#test").attr("disabled",true).attr("readonly",false); //입력불가, 값 안넘어감
	});
});
</script>
</body>
</html>
```
