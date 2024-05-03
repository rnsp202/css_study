#  css
##  css 작성 전 준비사항
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles로 css파일 배치
* ex) index.html, index.css 
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부 스타일시트**
* html파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부 스타일시트**
* 외부스타일시트의 장단점:
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정학히 관리하지 않으면 파일 관리가 어려울 수 있다.
* 내부스타일시트의 장단점: 
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기 편하다
- 단점 : 2개이상의 html파일을 동시에 디자인관리하는 것이 불가능하다.
## css 선택자
1. 태그 선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스 선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. 아이디 선택자 : `<h1 id="a"></h1>` -> `.#{속성:값;}`
4. 자손 선택자 : `<h1><em><span></soan></em></h1>` -> `h1 em span {속성:값;}`
4. 자손 선택자 : `<h1><em><em></em>/em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* ***HTML 자체 디자인을 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야 한다.***
* 초기와 CSS `reset.css` 공통파일(날짜나 프로젝트명 표기 금지) 
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴"(후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 글꼴 이름에 한글이나 공백이 있으면 꼭 ""안에 (영문만 있다면 ""없어도 됨) 
## font-size
* 웹 글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값 : px, 상대값 : %, em, rem(권장) 
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1) 
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` 8
* `#box #a .b p {}` 9
* `#wrap #box .a {}` 8
* `#wrap .a .b p {}` 8 
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box #a b p {}`
* `#box .a .b p {}`
* `#wrap #box a {}`
* `#box .a .b .c {}`
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은 색을 사용한다.
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값F RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 = #000, #FF00CC => #F0C
* rgba(red, green, blue, alpha) *최대색상 255
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식(그 외 크기인식불가능)
* `inline-block` : 내용만큼 크기인식(크기추가설정가능), 옆으로 정렬
### box-sizing
* `box-sizing:border-boz;`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성
* *속성 미적용 시 : w100+h100+padding-top20 = 100x120*
* *속성 적용 시 : w100+h100+padding-top20 = 100x100*
### width, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
## form요소와 속성
### `<form action="#" method=""></form>`
* action : 입력된 정보를 제출하는 최종 주소(URL)
* method : method의 값은 post, get으로 사용
* post : 양식 본문을 action URL에 그대로 전송
* get : 양식 본문을 URL 뒤 ? 에 이어붙여서 전송
### `<input type="" name="">`
* type : input의 속성
* name : input의 위치나 속성을 알수있게 해주는 이름(필수)
* readonly : 읽기 전용 속성
* autofocus, autocomplete : 창이 열리면 누르지 않아도 커서가 떠 있도록 해줌, 자동검색완성
* value : 값 입력 전 기본 값
* placeholder : 값 입력 전 떠있는 글자
* value와 placeholder의 차이점 : 후자는 입력하려고 누르면 사라짐
* maxlength : 글자 개수의 최대값 정하기
### `<textarea></textarea>`
* rows, cols : 입력창 길이 조절
* 사용용도 및 주의사항 : 안내사항 등을 보여줄 때, 안에 들어가있을 내용은 코드 내에서의 공백도 다 들어감.
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접 입력 가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터구분용), 선택양식(데이터 구분(개별데이터x, 그룹데이터구분용))
* `value` : 입력양식(초기값), 선택양식(개별데이터구분용)
## CSS Layout
### float, flex
* `float` : 형제 관계에 해당하는 block 또는 inline tag 왼쪽, 오른쪽 정렬할 때 사용
* 예 : ul-li*3개 정렬 ` ul li {float:left;}
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다
* 예 : ul-li 3개 정렬 `ul {display:flex;}
* flex 설정 시 **기본값** : 메인측(수평) 교차축(수직)
* `display:flex` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손x) flexible bow layout으로 처리하겠다!
* **flex 값**
- `flex-direction:row`	왼쪽->오른쪽 수평축 (기본값)
- `flex-direction:row-reverse`	오른쪽->왼쪽
- `flex-direction:column`	위->아래 수직축 변경
- `flex-direction:column-reverse`	아래->위
* **flex-warp** : 줄바꿈 처리
- `flex-wrap:wrap`	기본값(자동 줄바꿈) ex) 1 2 3
- `flex-wrap:wrap-reverse`	행 기준 역방향으로 자동 줄바꿈 처리
- `flex-wrap:nowrap`	줄바꿈하지 않음(한 줄 처리) 가변너비에 따라 자동으로 % 크기 변경
* **flex-flow** :  flex-direction과 flex-wrap을 묶음으로 처리 ex) `flex-flow:column nowrap`
* **justify-content** : 메인축의 정렬방법 설정
- `justify-content:flex-start`	items의 시작점 container의 시작점으로 정렬
- `justify-content:flex-end`	items의 시작점 container의 끝점으로 정렬
- `justify-content:center`	items을 메인축 기준 container에서 가운데 정렬
- `justify-content:space-between`	items을 container의 start, end 양끝 items을 배치하고 나머지는 고르게 정렬
- `justify-content:space-around`	items을 container안에서 균등한 여백을 포함하여 정렬
* **align-content** : 교차축의 아이템이 2줄 이상일 경우 정렬방법(flex-wrap:wrap 적용 후)
- `align-content:flex-start`	container의 start지점 기준 item 정렬
- `align-content:flex-end`	container의 end 지점 기준 item 정렬
- `align-content:center`	container의 가운데 위치 기준 item 정렬
- `align-content:space-between`	container의 start, end 에 양쪽 끝 맞추고 나머지 item 균등하게 정렬
- `align-content:space-around`	container에서 모든 item 균등하게 정렬
* **align-items** : 교차축의 아이템이 1줄일 경우 정렬방법
* 아이템 되는 자식 안에 속성 `flex:1;`하면 칸들이 자동으로 일정한 크기로 변함
* 각 아이템에 `order:(숫자);` : 원래 순서 상관없이 order 순서대로 정렬
## Font-Awesome
### font-awesome 전용 속성 값
* `.fa { font-weight: 600; font-family: 'Font Awesome 5 Free', 'Font Awesome 5 Brnads', 'Font Awesome 5 solid';}`
### css-font-awesome
* 1. font-awesome CDN  link  태그로 준비한다.
* 2. font-awesome 전용의 font-family와 weight를 설정한다.
* 3. font-awesome 적용이 될 태그를 준비한다.
* 4. 준비한 3번 태그에 가상선택자 (after or before)를 작성한다.
* 5. 가상선택자에 content속성을 입력해서 Unicode를 삽입한다.