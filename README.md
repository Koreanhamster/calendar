# calendar

HTML과 CSS를 이용하여 캘린더를 만들었습니다.

https://koreanhamster.github.io/calendar/4:5/index.html

![image](https://user-images.githubusercontent.com/95600994/161885009-3f5ba101-cb8d-485f-854c-cd1fe53dd6d2.png)


## 문제 
일요일에 해당하는 열만 빨간색으로 색깔을 변경하고싶어서, <colgroup>을 만들어 안에 <col span="1"> 을 줘서 일요일 열을 지정해주고 CSS로 color="red" 로 색깔을 지정해줬는데 먹히지 않았다.

 
 
## 왜 안되었나?
table에 계층이 있는데 각 cell은 row(tr)의 자식이지 column의 자식이 아니라 column의 속성을 상속받지 않는다.

지정한 열에는 border, background, width, visibility만 스타일링을 해줄 수 있다.

 

https://www.w3.org/TR/CSS2/tables.html#columns W3C의 설명 참고


## 해결책 
psudo class를 사용해서 td와 th의 첫 번 째 자식들을 선택해준 뒤 스타일링을 해 주었다.


td:nth-child(1),
th:nth-child(1) {
  color: red;
}
 

나머지 예외적인 holiday에 대해서만 따로 class를 줘서 색깔을 변경했다.


