
#20160706 FF ���� �ذ�
- ���� �����鿡�� ���� ���� �Ϳ��� ����
- ������ DOM���� �Ѿ���� �̺�Ʈ ��ü�� jQuery�� Event Handler�� ������ Event Object�� ���̴� ũ�ٴ� ��

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
FF�� window.event�� �������� �ʽ��ϴ�.
https://developer.mozilla.org/ko/docs/Web/API/Event

e = window.event || event; ���� "|| event"�� �ǹ� ���� �κ�������.
���� �̰� �Ʒ��� ���� �����ؼ� �ذ��߽��ϴٸ�...

$(document).on('click', '.wrap_checkbox', function (e) {
    e = e || window.event;

��� �� ���� �߸��� ����Դϴ�. (���� �����鿡�� ���� ������ �ع��Ƚ��ϴ�^^)

function�� argument�� �Ѿ���� e�� �׻� �����ϱ� ������.. �̹��� "|| window.event"�� �ǹ̾��� �ڵ尡 �Ź��Ƚ��ϴ�.
function�� argument�� �׻� �Ѿ���� ������ jQuery�� Event Handler Function���� JQuery�� �׻� �ϰ��� �̺�Ʈ ��ü�� �Ѱ��ֱ� ����������.
https://learn.jquery.com/events/event-basics/

�� e = e || window.event; ������ �׳� ���������� �˴ϴ�.

�����

```javascript
//<button>jquery event test</button>
//jQuery�� Event Handler ����
$('button').click(function(e) {
    console.log(e.target);
});

// <button onclick="testDomClick(event)">dom event test</button>
//onclick���� ����� ��
function testDomClick(e) {
    console.log(e.target);
}

//event listener�� ��� ���� ���
function testDomClick(e) {
    e = e || window.event;
    console.log(e.target);
}
```