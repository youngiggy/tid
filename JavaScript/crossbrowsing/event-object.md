
#20160706 FF 오류 해결
- 오늘 팀원들에게 메일 보낸 것에서 발췌
- 요점은 DOM에서 넘어오는 이벤트 객체와 jQuery의 Event Handler로 들어오는 Event Object의 차이는 크다는 것

```javascript
clickItem: function () {
    $(document).on('click', '.wrap_checkbox', function () {
        e = window.event || event;

        if (!$this$.clickEventValidate(this, e)) {
            return false;
        }

        $this$.clickItemImpl(this);
    });
},
```
FF는 window.event를 지원하지 않습니다.
https://developer.mozilla.org/ko/docs/Web/API/Event

e = window.event || event; 에서 "|| event"는 의미 없는 부분이지요.
저는 이걸 아래와 같이 수정해서 해결했습니다만...

$(document).on('click', '.wrap_checkbox', function (e) {
    e = e || window.event;

사실 이 역시 잘못된 방식입니다. (어제 팀원들에게 거짓 진술을 해버렸습니다^^)

function의 argument로 넘어오는 e는 항상 존재하기 때문에.. 이번엔 "|| window.event"가 의미없는 코드가 돼버렸습니다.
function의 argument가 항상 넘어오는 이유는 jQuery의 Event Handler Function에는 JQuery가 항상 일관된 이벤트 객체를 넘겨주기 때문이지요.
https://learn.jquery.com/events/event-basics/

즉 e = e || window.event; 라인을 그냥 지워버리면 됩니다.

참고로

```javascript
//<button>jquery event test</button>
//jQuery의 Event Handler 예시
$('button').click(function(e) {
    console.log(e.target);
});

// <button onclick="testDomClick(event)">dom event test</button>
//onclick에서 사용할 때
function testDomClick(e) {
    console.log(e.target);
}

//event listener로 등록 됐을 경우
function testDomClick(e) {
    e = e || window.event;
    console.log(e.target);
}
```