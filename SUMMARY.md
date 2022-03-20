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
