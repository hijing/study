# attr() 메소드 : 속성 값 지정, 속성 값 불러오기

1) attr() 메소드
- HTML 에서 사용하는 태그 안에 속성들의 값을 불러오거 변경하는 작업을 하는 메소드 입니다. 
  예를 들면 <input type="hidden"/> 일 경우 attr("type", "text") 설정을 하시면 type 속성 값이 변경이 됩니다.
  만약에 attr("type") 일 경우 type 속성 값을 가지고 오게 됩니다. 
  태그에 속성이 없을 경운는 자동으로 속성을 생성해서 값을 설정 합니다.
  메소드에 들어가는 인자 개수에 따라 속성 값을 설정 하거나 불러 올 수 있습니다.

1_1) 인자
- 현상을 일으키는 원인이나 조건이 되는 요소를 말합니다.

2) 사용방법
// searchCondition 이름을 가진 태그에 value 값 지정
$("input[name='searchCondition']").attr("value", null); 

// searchCondition 이름을 가진 태그에 action 속성 값을 지정
$("form[name='actionForm']").attr("action", "<c:url value='/imgzone/mgr/list.do'/>");
