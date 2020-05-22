# 라디오버튼 및 텍스트박스 비활성화시키기 "readonly" "disabled"

btn이라는 라디오버튼을 비활성화 시킬 경우.
$("input[name='btn']").attr('disabled',true);

title이라는 텍스트박스를 비활성화 시킬 경우,
$("input[name=email]").attr('readonly',true);

둘 다 false 적용 시, 다시 활성화
