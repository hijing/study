# Ajax는 페이지 이동없이 화면 갱신이 가능
HTTP 리퀘스트에 대해 비동기 동작을 한다.

속성값으로는 다음이 사용된다.

|속성|값|
|----|--|
|url|리퀘스트 보내게 되는 URL 값을 Stirng으로 입력|
|accepts|서버에서 전송 받을 MIME type을 Object방식으로 설정|
|async|기본값은 true이며 비동기 방식으로 진행할 건지에 대한 셋팅|
|beforeSend|리퀘스트 보내기전에 작동하는 함수를 입력|
|complete|성공, 실패, 에러등 모든 상황이 종료된 이후의 함수를 입력|
|data|리퀘스트 URL과 함께 입력될 데이터를 Object, Array, String 형식으로 입력|
|method(type)|리퀘스트전송에 대한 메소드 타입을 입력 (예 : "GET" , 또는 "POST" 등) |
|error|전송이 완료된 후 에러상황에 대한 함수를 입력|
|success|전송이 완료된 후 성공상황에 대한 함수를 입력|

<br>

속성값은 더 많이 있지만 자주 사용하는 속성들은 이 정도이다.

<br>

기본 예제코드
```
$.ajax({
  url: "/json/people",
  data : {"id" : "admin"},
  beforeSend: function( xhr ) {
    console.log('리퀘스트 보내기 전에 데이터 조작가능');
  },success: function(d){
    console.log('서버에서 받은 데이터 = ' + d);
  }, error : function(e){
    console.error('에러발생');
  }
})
```
<br>

ajax를 통해 DOM을 추가하는 예제
```
$.ajax({
  url: "test.html",
  cache: false
}).done(function( html ) {
    $( "#results" ).append( html );
  });
});
```
<br>
위의 예제는 test.html이 동적으로 작동한다는 가정을 하고 cache를 false로 하고 사용<br>
브라우저의 cache내용을 받지 않고 서버에서 새로 받아오는 것으로 이해<br>
<br>
그리고 ajax가 종료되면 done함수의 results 엘리먼트에 서버에서 받아온 HTML을 엘리먼트 뒤에 추가(append)

