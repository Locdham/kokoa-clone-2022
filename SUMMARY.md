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
