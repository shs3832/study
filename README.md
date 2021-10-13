##### 📌 반응형으로 변할시 스크롤바가 나오는지 주의 나온다면 문제일수있지만 상황에 따라 다를 수 있다

##### 📌 아이디-> 전체적인 틀에 사용 / 클래스-> 세부적이고 반복적인 곳에 사용 -> 코딩 규칙(컨벤션)이 있다면 그것에 따르는 것이 좋다.

##### 📌 자식요소에 float 사용시 전체 박스에는 overflow:hidden 을 하는 한 가지의 방법이 있다. 가상요소 만들어서 float 해제 하는 방법이 좋음

##### 📌 html5shiv -> 시멘틱 태그를 구형 브라우저에 지원해주기 위한 스크립트 . 지금은 사용되지 않는다

##### 📌 modernizr -> 현재 사용자가 쓰는 브라우저의 특징을 응답해줌 이용 가능한 것들을 클래스명으로 알려줌 -> 프로젝트에서 사용할 특징을 선택해서 빌드를 하는 방법으로 현업에서는 사용된다

##### 📌 box-shadow : x y blur-radius spread-radius / inset -> 내부에 효과를 주는 속성 / 앞뒤 위치에 쓰기 가능(하지만 일관성 있게 위치를 통일하는 것이 좋다)

##### 📌 border-radius -> 동일하게 4면을 다 처리하는 스타일에만 익숙했는데, border-radius: 5px 0; top-left&bottom-right 에만 효과를 주는 디자인을 알게됨

##### 📌 < : `&lt;` ||| > : `&gt;` -> 기호는 코드로 처리

##### 📌 컬러코드는 3자리 혹은 6자리로 작성

##### 📌 일관성 있는 코드가 좋은 코드

##### 📌 스타일 시트의 순서는 우선순위로 적용되야 할 시트(예:reset.css)들 순서로 먼저 연결하고 ->라이브러리에 관련된 스타일 시트-> 마지막에 내가 작업한 페이지 스타일 시트가 오는 순서가 좋다.

---

10/8

###### 📌 position:absolute 를 기본으로 바꿀 때 -> position:static; 으로 설정 (static : normal flow를 따르는 기본값)

###### 📌 다양한 고밀도 디스플레이 기기가 늘어남에 따라 해상도에 따라서 이미지를 제공하는 방법으로 간다. 고해상도의 이미지를 불러오면 사이트가 느려지기 때문에 최적화된 이미지를 불러오는게 중요하다.

-   (일반 모니터) x1 , (레티나 모니터) x2, (모바일) x3, x4
-   @media only screen and min-device-pixel-ratio:1.5 -> 화면 비율이 1.5 이상 됬을 때 -> 미디어 쿼리로 비율을 설정해서 이미지 해상도를 고르는 방법 -> 번거로워서 좋은 방법은 아니지만 방법 중 하나
-   srcset 을 사용하면 브라우저는 적합한 이미지를 선택해서 가져온다. html 5.1부터 img tag에 속성 추가됨
-   배경이미지로 해서 미디어 비율에 따라 이미지를 불러오는 방법

###### 📌 figure : 독립적인 콘텐츠 표현, img 태그를 묶을 때 자주 사용한다. figcaption 요소를 사용해 추가 설명을 붙인다 -> figure보단 picture 태그를 많이 사용한다

---

10/12

###### 📌 css filter : 포토샵에서 사용되는 그래픽 효과를 설정 가능하다. -> 최신문법은 can I use 사이트에서 브라우져별 적용되는지 확인 //비슷한 속성으로 mix-blend-mode 가 있다.

-   blur(px), brightness(%):밝고 어두움, contrast(%):이미지 대비, drop-shadow(), grayscale(%), hue-rotate(deg):이미지 색조
-   saturate(%):이미지 채도, sepia(%), invert(%):이미지 반전, opacity(%)

###### 📌 iframe 영역을 잡기 위해서 가상으로 패딩을 % 값으로 설정해서 영역을 잡아주었다. 반응형을 css로 하는 편리한 방법.. <<16:9 = 100%(width):56.9%(height) >>

###### 📌 icon을 넣는 방법 중 가상요소를 만들어서 넣는 방법이 있다.

-   가상요소 콘텐츠에 "역슬러시+ 해당 아이콘의 유니코드"를 입력한다
-   font-weight를 추가로 입력해줘야 한다. 아이콘의 스타일에 따라서 값을 넣어줘야함
    --- solid : 900 // regular,brands : 400 // light : 300
-   font-family 도 버전에 따라 입력해줘야함. 해당 버전은 FontAwesome;
-   정확이 입력하지 않으면 □ 으로만 표시된다.

###### 📌 section 혹은 article엔 h 태그가 들어가야한다

###### 📌 클래스로 공통 여백 스타일을 만들어서 여백을 지정하는 것보단 태그마다 개별로 지정하는 것이 더 좋은 방법.

###### 📌 스타일 지정 할 때 태그에 바로 하는 것보단 클래스를 지정해서 클래스에 스타일을 적용하자

###### 📌 해상도 변경시 최적화 이미지 바뀌는 부분--> .img-retina {display: initial`}`

-- initial 키워드는 초깃값(기본값)을 요소에 저장한다. 초깃값은 브라우저가 지정한다. 여기서는 img 태그의 초깃값을 해상도 변경시 복구 했다. img tag의 기본값은 display:inline
-- inline : 전후 줄바꿈 없이 한 줄에 다른 요소들과 나란히 배치된다. 너비와 높이 속성을 지정해도 무시가되는데 이는 해당 태그가 마크업하고 있는 콘텐츠의 크기 만큼만 공간을 차지하도록 되어있기 때문이다. 여백도 좌우만 반영. 상하는 반영x
-- inherit 키워드를 사용한 속성은 부모 요소로부터 해당 속성의 계산값을 받아 사용한다.

---

10/13

###### jquery로 요소의 넓이 측정 방법

-   window.width() : padding까지 제외한 순수하게 요소의 내부 크기만을 측정 내부 넓이
-   window.innerWidth() : 윈도우 안쪽 폭, 브라우저 윈도우의 뷰포트 너비로, 수직 스크롤바가 존재한다면 포함한다. / 내부넓이 + padding
-   window.outerWidth() : 브라우저 윈도우 바깥쪽의 폭을 얻어온다.윈도우의 바깥경계를 포함한 너비(폭)을 담고 있다. 브라우저 윈도우의 사이드바와 가장자리 경계선을 포함한 폭을 나타내어 준다. 읽기전용이며 기본값이 없다.
    내부넓이 + padding + border // $(window).outerWidth(true); -> 내부넓이 + padding + border + margin
