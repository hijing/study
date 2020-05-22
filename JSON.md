# 자바스크립트와 JSON
JSON은 자바스크립트의 객체 표기법을 제한하여 만든 텍스트 기반의 데이터 교환 표준입니다.
따라서 JSON 데이터는 자바스크립트가 자주 사용되는 웹 환경에서 사용하는 것이 유리합니다.
 
자바스크립트에서 JSON 데이터를 분석하고 사용하는 것은 매우 간단합니다.
자바스크립트는 JSON 데이터를 처리하기 위한 다음과 같은 메소드를 제공하고 있습니다.
 
1. JSON.parse()
2. JSON.stringify()
3. toJSON()


## JSON.parse() 메소드
JSON.parse() 메소드는 JSON.stringify() 메소드와는 반대로 인수로 전달받은 문자열을 자바스크립트 객체로 변환하여 반환합니다.
문법
JSON.parse(text)
 
text에는 변환할 문자열을 전달합니다.
이때 해당 문자열은 반드시 유효한 JSON 형식의 문자열이어야 합니다.
만약 JSON 형식에 맞지 않는 문자열을 전달하면, 자바스크립트는 오류를 발생시킬 것입니다.

JSON.parse() 메소드는 오직 JSON 형식의 문자열만을 변환할 수 있습니다.

'''
<script>
		// JSON 형식의 문자열
		var data = '{"title": "memo", "count": 3}';
		
		var obj = JSON.parse(data);	// JSON 형식의 문자열을 자바스크립트 객체로 변환함.
		document.getElementById("json").innerHTML = obj + "<br>";
		document.getElementById("json").innerHTML += obj.title + ", " + obj.count;
	</script>
'''

==>
'''
[object Object]
memo, 3
'''




## JSON.stringify() 메소드
JSON.stringify() 메소드는 인수로 전달받은 자바스크립트 객체를 문자열로 변환하여 반환합니다.
문법
JSON.stringify(value)
 
value에는 변환할 자바스크립트 객체를 전달합니다.
이 메소드는 UTF-16으로 인코딩된 JSON 형식의 문자열을 반환합니다.
'''
<script>
		var data = {title: "memo", count: 3};	// 자바스크립트 객체
		
		var obj = JSON.stringify(data);	// 자바스크립트 객체를 문자열로 변환함.
		document.getElementById("json").innerHTML = obj;
</script>
'''


==>
'''
{"title":"memo","count":"3"}
'''




## toJSON() 메소드
자바스크립트의 toJSON() 메소드는 자바스크립트의 Date 객체의 데이터를 JSON 형식의 문자열로 변환하여 반환합니다.
따라서 이 메소드는 Date.prototype 객체에서만 사용할 수 있습니다.
 
toJSON() 메소드는 접미사 Z로 식별되는 UTC 표준 시간대의 날짜를 ISO 8601 형식의 문자열로 반환합니다.
따라서 이 문자열은 언제나 24개나 27개의 문자로 이루어지며, 다음과 같은 형식을 따릅니다.

YYYY-MM-DDTHH:mm:ss.sssZ
또는
±YYYYYY-MM-DDTHH:mm:ss.sssZ

'''
<script>
		var date = new Date();		// 자바스크립트 Date 객체
		var str = date.toJSON();	// Date 객체를 JSON 형식의 문자열로 변환함.

		document.getElementById("json").innerHTML = date + "<br>";
		document.getElementById("json").innerHTML += str;
</script>
'''


==>
'''
Thu Feb 06 2020 17:51:21 GMT+0900 (한국 표준시)
2020-02-06T08:51:21.672Z
'''
