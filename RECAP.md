# 6.1 Sign Up Screen part One

기존엔 html 작업을 전부 하고 css 작업으로로 넘어갔지만, 본 코스에선 html과 css를 함께 작업합니다.

0. index는 대부분의 웹서버가 가장 먼저 읽는 파일입니다. (이는 브라우저가 가진 디폴트 속성입니다.)

1. '!'는 html 기본 서식을 빠르게 입력할 수 있는 단축키입니다.

2. column이라는 이름은 매우 일반적이기 때문에 (다른 html 파일에서도 많이 사용되는 이름이라), 구분을 짓기 위해 '부모 요소**자식요소'로 이름을 짓습니다.
   예)
   〈div id="status-bar"〉
   〈div class = "status-bar**column"〉 〈/div〉
   〈/div〉

3. 〈!--내용--〉은 브라우저에게 보이지 않고, 사용자만 볼 수 있는 일종의 메모입니다. (물론 개발자 도구로는 볼 수 있습니다. 구현되는 페이지에 드러나지 않을 뿐입니다.)

# 6.2 Block Element Modifier

BEM
block
block**element
block**element--modifier
내가 내 코드를 다시 볼 때, 남들이 내 코드를 찾아 볼 때 이해에 도움을 줌

BEM(Block Element Modifier) —추천 규칙

- block : .btn {}
- elements : .btn--price {}
- modifiers : .btn--big {}

단점 : 클래스 선언 종류가 많아서 코드가 길어진다.

- 참고
  [BEM - Block Element Modifier](http://getbem.com/introduction/)
  [BEM 101 | CSS-Tricks](https://css-tricks.com/bem-101/)
  [BEM CSS 방법론](https://nykim.work/15)

# 6.3 Font Awesome

- 아이콘을 추가하는 데에는 두 가지 옵션이 있다.

1. 직접 아이콘을 구하는 방법(직접 이미지를 만들고 추출하거나 svg파일을 이용.
   svg는 픽셀이 없는 이미지 파일형식. 수학으로만 구성된 형식)
2. Heroicons, FontAwesome에서 가져오기

- FontAwesome에서 가져온 kit code 스크립트는 항상 맨 마지막줄에 있어야한다.
  body 태그를 닫기 직전.
- 'i'는 icon의 줄임말.

# 6.4 Sign-Up Screen part2

헤더작성시,
마찬가지로 어떤 페이지든 공통적으로 헤더를 가지고 있으므로 구분 가능하게 클래스를 만들어줘야함

form 작성
id pw 입력창과 버튼두개
form에서 버튼은 type submit으로
그리고 이번 프로젝트에 form은 많이 필요하지 않기 때문에 클래스 아이디를 고민안해도됨

- input 태그에 type을 "submit"으로 하는 방법
- 링크는 무척 많아서 하나만을 위한 id나 class를 추가할 필요는 없다. form 태그안에 넣어둠

# 6.5 Status-bar CSS

- HTML에 CSS를 작성하고 싶을 때, "link:css"라 하고 엔터를 치면 자동 완성 된다.
- font-family를 이용하여 서체를 변경할 수 있다.
- Google fonts 웹사이트에서 원하는 폰트를 가져다 쓰면 된다.
- 사용하지 않는 스타일까지 모두 선택하면, 하나의 스타일을 선택한 것보다 불러오는데 시간이 오래 걸릴 수 있다. → 사용하지 않을 스타일을 추려내는 것도 중요하다.
- css hack(기술) → 레시피와 같은 것
- 아이콘의 크기를 키워줄려면, 아이콘 이름에 2x or lg 등을 붙여준다.

# Hack status-bar 3등분 기술

사용된 CSS hack 에 대해서..

1. body 100% 안에 있는 status-bar 전체를 우선 화면에서 가운데 위치하도록
   justify-content:center; 를 적용합니다. 그러면 전체 요소들이 모두 가운데 위치하게 됩니다.

2. status-bar**column에 각각 33% 값을 주어 status-bar를 3등분 합니다.
   그러면 스크린을 줄이거나 늘이더라도 status-bar**column들은 그 안에서 왼쪽 정렬로 위치하게 됩니다.

3. 1번째 column은 가장 왼쪽(기본값), 2번째는 가운데(center) 그리고 3번째는 가장 끝(flex-end)으로 위치시키면 시계는 가운데에 있고 나머지 요소는 가장자리에 위치하게 됩니다.

# 6.6 SignUp Screen part03

- 리셋 CSS는 CSS 파일이다. 브라우저에 기본적으로 적용되어 있는 스타일을 초기화 해준다.
- 먼저 브라우저 스타일을 없애고, 직접 디자인 하는게 더 좋은 방법이다.
- styles.css에서 작성한 한 부분도 따로 css파일을 만들어 분리해주는 것이 깔끔하게 작업할 수 있는 방법이다. → CSS 코드를 여러 파일로 분할했다가 다시 합친다.
- h1, p tag같은 텍스트를 다루는 tag들을 가운데 정렬 할 때는 text-align:center 이용

# 6.7 Log-in form part01

Custom property
Reset CSS
input:focus {
outline: none;
}
Variable CSS
:root {
--yellow: #fae100;
}

# 6.8 NOT 속성

border설정은 input {border: none;}에서 시작함.
input:focus를 먼저쓰면 색을 설정해줘도 border가 없으니 적용이 불가능하고,
그 이후에 not으로 border-bottom만 정의해주니 focus해도 색변화가 없다.

input:not([type="submit"])을 먼저쓰면 border-bottom이 정의되므로
input:focus에서 border-color가 border-bottom에 적용되어 원하는대로 나온다.

- 가상 클래스 선택자(pseudo element)
- :not()→ 뭔가가 적용되는 걸 원하지 않을 때 사용한다.
- [ ] 사이에 쓰인 것들은 특성 선택자(attribute selector)이다.
- cursor: pointer;로 버튼 위의 커서를 변경할 수 있다.
- color:inherit;는 부모로부터 색을 상속받는 것이다.

# 6.9 Recap and Forms

Form은 아주아주 중요한 요소 두가지를 가지고 있다

- Action : 어떤 페이지로 data를 보낼건지 지정할 수 있다
- Method :
  └ Post : 백엔드서버에 정보를 전송하는 방식, 서버를 설정하여 사용하므로 이번강의에서 사용불가 하다
  └ Get : URL에 포함되어도 상관없는 정보들을 GET방식으로 사용, username/password는 사용하면 안된다
- #login-form ... 으로 썼찌만, .login-from\_\_\_ ... 으로 써도된다. 더 편한 방식을 택하면 된다.
- CSS 파일에서 주석처리는 /\* \*/로 감싸주면 된다.
- styles.css 파일에는 font-family와 같이 모든 스크린에 적용될 수 있는 스타일을 써놓는다.( or 모든 스크린의 background-color) 이는 하나의 방식이고, 자신만의 편한 방식을 택하면 된다.
- form은 중요한 2가지 속성(attribute)을 가지고 있다. 하나는 action이고, 다른 하나는 method이다.

# 6.10 Navigation Bar part one

Navigation-bar 네비게이션바

- navigation 안의 ul 안에 많은 li들로 구성되는데, 검색엔진 구글도 navigation을 찾아서 ul의 li 안에 있는 link를 가져오게끔 설정되어 있다.
- VSC의 단축키로 navigation에서 하위메뉴까지 한번에 자동 완성 시킬 수 있다.
  → nav>il>li\*(필요한 갯수)>a
  → 그 후 #과 tab만으로 간편하게 작성이 가능하다.(수정하다보면 다음 tab이 옳게 먹히지 않는다.)
- 점 3개는 ellipsis라고 한다.
- 속성과 class 이름이 똑같아도 상관없다.
- 메인 styles.css에 다른 요소의 css를 import 할 때, 순서를 지키는 것이 정말 중요하다.

# 6.11 Navigation Bar part Two

- 위치를 고정 시키기
- position : fixed
- 배열이 깨지는 경우 width : 100% 설정
- 고정할 위치 (아래 인 경우 bottoom : 0;)과 같이 설정
- box-sizing:border-box를 사용해 아이콘들이 한 줄로 보이게 함

# 6.12 - box-sizing:border-box

CSS에서 200px 크기의 box에 50px의 padding을 원할 경우,
총 크기 200px, (width 150, padding 50 실제 내용 150)의 box를 생각해서
padding : 50px, width : 200px 로 입력하지만,
이렇게 하면 CSS에서는 padding을 50px 주고, 200px의 box width는 유지하려 하므로,
총 크기 250px (width 200, padding 50 실제 내용 200)의 box를 가지게 된다.
box-sizing : border-box 를 입력할 경우,
padding을 입력해도 box사이즈를 신경쓰지 않는다는 의미이다.
따라서, 처음에 원했던 50 padding, 150 box 를 가지게 된다.
CSS에게 "패딩을 줘도 신경쓰지마! 내박스 사이즈 늘리지 말아줘" 라는 말이다

# 6.13 Navigation Bar part Three

- border을 사각형으로 만들고 싶다면, radius를 width의 절반값을 주면된다.
- position: absolute;는 정중앙. absolute는 해당 element의 가장 가까운 relative를 가진 부모 기준으로 움직인다. 기본적으로 body가 그에 해당되며, 따로 원하는 기준이 있다면 그 container에 position: relative;를 준다.

# 6.14 Screen Header

# 6.15 Friends Screen part One

CSS에서 두 객체의 겹침을 피하는 방법은 무엇입니까?

- 고정 위치 대신 top : 0; 과 함께 position : sticky; 를 사용할 수 있습니다. 그러면 겹침을 피하기 위해 다른 요소를 추가 할 필요가 없습니다.

고정 위치

이것은 기본적으로 상대 위치와 고정 위치 사이의 하이브리드로, 위치 지정 요소가 특정 임계점 (예 : 뷰포트 상단에서 10px)까지 스크롤 될 때까지 상대적으로 위치 된 것처럼 작동 한 후 고정됩니다.

# 6.16

사진 사이즈 변경 시, 가로 세로 비율 그대로 유지하고 싶으신 분들은 object-fit: cover; 추가한다

# 6.17 User Component part Two

modifier 로 .user-component**avatar--xl을 사용했는데,
그럴필요 없이 기존에 있던 user-component**avatar 에서 width:80, height:80을 하면 되지 않을까?

- 그렇게 되면 나중에 채팅페이지나 다른곳에서 쓰일 \_\_avatar가 다 80x80으로 변경되니까 따로 클래스를 준것!

# 6.18 Finishing Friends Screen

# 6.19 Chats Screen part one

# 6.20 Chats Screen part Two

badge.css 생성: 빨간 동그라미
.nav-notification -> 네비 바에 뜬 알람 (아이콘의 우측 상단에 오게 함)
각 스크린의 네비는 badge nav-noti 두 가지 클래스를 모두 적용해주고
챗 스크린에서 톡 알림은 badge 클래스만 이용

챗 스크린에서 뱃지와 시간을 정렬하기 위해서
user-component\_\_column:last-child
display: flex
flex-direction: column
align-items: flex-end

그런데 이렇게 하면 friends screen에서 channel에서 2>가 세로로 정렬됨.
이를 막기 위해 2와 >를 한 div에 묶어준다.

# 6.21 Find Screen Part One

icon 위에 빨간점 component로 만들기

1. components 파일에 point.css 생성

2. point.css에 red point에 대한 코드 작성
   .point {
   background-color: tomato;
   width: 5px;
   height: 5px;
   border-radius: 2.5px;
   position: absolute;
   right: -6px;
   top: -7px;
   }

3. styles.css 에 import
   @import "components/point.css";

4. find.html 에 해당코드 작성 ( div class=“point” )
   점 찍고 싶은 span 사이에 넣어주기

5. screen-header.css에서 relative 관계 설정해주기
   .screen-header\_\_icons span{} 에 position: relative 설정

6. Boom해주기

# 6.22 Find Screen Part Two

.recommended-friends span {
font-size: 18px;
text-align: center;
margin: 100px 0px;
/_ 마진이 적용안되는 이유는 inline 이기 때문이다. block으로 바꿔라! _/
display: block;
color: var(--font-color-gray);
}

# 6.23 Find Screen Part Three

- HTML 코드에선 대문자를 나타내려고 해도, 우선 소문자로만 작성한다. 대문자는 디자인적인 요소이기 때문에, CSS 파일에서 작성해줘야 한다.
- text-transform: uppercase; 대문자로 만들기.

# 6.25 More Screen part One

1. Add 2 more icons on More screen
   아이콘 추가 작업건

.icon-row {
display: flex;
flex-wrap: wrap;
/_ justify-content: space-between; _/
}

.icon-row\_\_icon {
display: flex;
flex-direction: column;
align-items: center;
width: 25%;
padding: 10px;
box-sizing: border-box;
transition: color 0.3s ease-in-out;
color: rgba(0, 0, 0, 0.6);
}

2. Add animation for 6 icons
   모든아이콘 애니메이션 추가건

.icon-row\_\_icon:hover {
cursor: pointer;
color: black;
}

# 6.26 More Screen part Two

# 6.27 Settings Screen part One

/_ 정중앙 센터 맞추기 핵꿀팁!!! _/
.alt-header**column:first-child {
margin-right: auto;
}
.alt-header**column:last-child {
margin-left: auto;
}
/_ 정중앙 센터 맞추기 핵꿀팁!!! _/

width 33% border-box

# 6.28 Settings and Chat Screen part One

# javascript:history.back();

모든 페이지에서 settings.html로 연결할수 있게 해 놓으신분들 중 뒤로가기 버튼을 눌렀을때 more.html이 아니라 이전 html 페이지로 연결되게 하실 분들은 href 값으로 "javascript:history.back();" 을 주면 됨

# text-align:right;

alt-header:last-child의 돋보기 아이콘과 햄버거아이콘 사이의 간격을 주기위해 아이콘에 margin을 적용했더니, 이름이 중앙에서 왼쪽으로 밀려납니다. 이름에 또 따로 position:relative적용 후 좌우로 움직이는 방법외에 이름을 중앙에 정렬하는 방법 있을까요??

# 6.29 Chat Screen part Two

1. z-index
   default: 0
   숫자가 작을수록 낮은 layer, 클수록 위의 layer
   fixed, absolute position에 이용 가능.

2. fixed를 모두 sticky로 바꾸어 적용

3. .alt-header\_\_column {
   width: 33%;
   }

/_ 정중앙 센터 맞추기 핵꿀팁!!! _/
.alt-header**column:first-child {
margin-right: auto;
}
.alt-header**column:nth-child(2) {
text-align: right;
}
.alt-header\_\_column:last-child {
margin-left: auto;
display: flex;
justify-content: flex-end;
}
