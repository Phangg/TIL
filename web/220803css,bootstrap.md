### CSS Layout

---

- Display
- Position
- Float
- Flexbox
- Grid
- 기타 ( 반응형 웹 / 미디어 쿼리 )

---

- **Float ( 요즘은 잘 사용하지 않음 )**
  
  - 박스를 왼쪽 혹은 오른쪽으로 이동 시켜서 텍스트를 포함 / 인라인 요소들이 주변을 wrapping 하도록 함
  
  - 요소가 Normal flow 를 벗어나도록 함 (띄우는 것임)
  
  - 속성
    
    - none : 기본 값
    - left : 요소를 왼쪽으로
    - right : 요소를 오른쪽으로
  
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
        .box {
          width: 150px;
          height: 150px;
          border: 1px solid black;
          background-color: crimson;
          margin: 20px;
        }
        .left {
          float: left;
        }
        .right {
          float: right;
        }
      </style>
  </head>
  <body>
    <div class="box left">float left</div>
    <div class="box left">float left</div>
    <div class="box right">foat right</div>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptates perferendis consequuntur quisquam est voluptatum excepturi, enim impedit cumque quos eveniet deleniti eligendi. Provident quae dolor optio consequuntur dolorem ad alias.
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores perferendis harum, ea earum aliquam sint praesentium, animi atque tempore ipsa, ullam fuga facilis odio accusantium. Iure quis iusto voluptatem quam!
    </p>
  </body>
  </html>
  ```
  
  
  
  - .clearfix::after 사용 (초기화?)
    - header에 의미를 특별하게 가지지 않는 클래스를 만들어주는….

---

- **Flex box**
  
  - 행과 열 형태의 아이템들을 배치하는 1차원 레이아웃 모델
  
  - 수동 값 부여 없이
    
    - 수직 정렬 가능
    - 아이템의 너비와 높이 혹은 간격을 동일하게 배치
  
  - 축
    
    - main axis 메인 축
    - cross axis 교차 축
  
  - 구성 요소
    
    - Flex Container 부모 요소 ( 정렬하고자 하는 컨테이너에 display: felx; 선언 )
    - Flex Item 자식 요소
  
  - **속성**

- 배치 속성
  
  - flex-direction : main axis 방향 설정
    - row (기본 값) :
    - row-reverse
    - column
    - column-reverse



- flex-wrap : 요소들이 강제로 한 줄에 배치 할 지 설정 / 아이템이 컨테이너를 벗어나지 않도록 함
  - nowrap (기본 값) : 한 줄에 배치
  - wrap : 넘치면 다음 줄로 배치



- 공간 나누기
  - justify-content : main axis 를 기준으로 공간 배분
    - flex-start (기본 값) : 아이템들을 axis 시작점으로
    - flex-end : axis 끝으로
    - center : axis 중앙
    - space-between : 아이템 사이의 간격을 균일하게
    - space-around : 가질 수 있는 영역 반 나눠서 양쪽 ex) 1:2:2:1
    - space-evenly : 전체 영역에서 각 아이템 사이 간격 균일하게 분배 ex) 1:1:1



- align-content : cross axis 를 기준으로 공간 배분
  
  ( 아이템이 한 줄 배치되는 경우 확인 불가 )
  
  - flex-start (기본 값) : 아이템들을 axis 시작점으로
  - flex-end : axis 끝으로
  - center : axis 중앙
  - space-between : 아이템 사이의 간격을 균일하게
  - space-around : 가질 수 있는 영역 반 나눠서 양쪽 ex) 1:2:2:1
  - space-evenly : 전체 영역에서 각 아이템 사이 간격 균일하게 분배 ex) 1:1:1



- 정렬
  - align-items (모든 아이템을 cross axis 기준으로) * 두 줄 이상
    - stretch (기본 값) : 컨테이너 가득 채우기
    - flex-start : 위
    - flex-end : 아래
    - center : 중앙
    - baseline : 박스가 아닌 content의 밑 라인에 맞추기 (text의 baseline)



- align-self (개별 아이템을 cross axis 기준으로) * 컨테이너 아닌, 개별 아이템에 적용
- 기타 속성
  - flex-grow : 남은 영역을 아이템에 분배
  - order : 배치 순서

# Bootstrap

---

- 프론트엔드 라이브러리 중 하나 ( 인기 있는! )

- **CDN**

- Content Delivery(Distribution) Network
  
  - 컨텐츠 (CSS, JS, Image, Text 등) 을 효율적으로 전달하기 위해
    
    여러 노드에 가진 네트워크에 데이터를 제공하는 시스템
    
    [Get started with Bootstrap · Bootstrap v5.2](https://getbootstrap.com/docs/5.2/getting-started/introduction/)

- link 는 title과 head사이

- script는 닫는 body태그 바로 위

---

### Bootstrap 기본 원리

---

- **spacing ( Margin and padding )**
  
  
  
  - property
    - m - margin
    - p - padding
  - sides
    - t - top
    - b - bottom
    - s - start (left)
    - e - end (right)
    - x - left & right
    - y - top & bottom
    - blank - all 4 sides
  - size
    - 0 - 0
    - 1 - 0.25rem (4px)
    - 2 - 0.5rem (8px)
    - 3 - 1rem (16px)
    - 4 - 1.5rem (24px)
    - 5 - 3rem (48px)
    - auto
  
  ```html
  <h2>Spacing</h2>
    <div class="mt-3 ms-5 box">margin top3 ms-5</div>
    <div class="m-4 box">margin 4</div>
    <div class="mx-auto box">mx-auto/가운데 정렬</div>
    <div class="ms-auto box">ms-auto/오른쪽 정렬</div>
  ```
  
  

- **color**
  
  ```html
  <h2>Color</h2>
    <div class="bg-primary">이건 파랑</div>
    <div class="bg-secondary">이건 회색</div>
    <div class="bg-danger">이건 빨강</div>
    <p class="text-success">이건 초록색</p>
    <p class="text-danger">얘도 빨간색</p>
  ```
  
  

- **text**
  
  ```html
  <h2>Text</h2>
    <p class="text-start">text-start</p>
    <p class="text-center">text-center</p>
    <p class="text-end">text-end</p>
    <a href="#" class="text-decoration-none text-dark">Non-underline-Link</a>
    <p class="fw-bold">fw-bold</p>
    <p class="fw-normal">fw-normal</p>
    <p class="fw-light">fw-light</p>
    <p class="fst-italic">fst-italic</p>
  ```
  
  

- **display , position**
  
  ```html
  <h2>Position</h2>
    <div class="box fixed-top">fixed-top</div>
    <div class="box fixed-bottom">fixed-bottom</div>
  
    <button type="button" class="btn btn-primary position-relative">
      Mails <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-secondary">+99 <span class="visually-hidden">unread messages</span></span>
    </button>
  
    <div class="bigbox position-relative">
      <div class="box position-absolute top-0 start-0">top0/start0</div>
      <div class="box position-absolute top-0 end-0">top0/end0</div>
      <div class="box position-absolute bottom-0 start-0">bottom0/start0</div>
      <div class="box position-absolute bottom-0 end-0">bottom0/end0</div>
    </div>
  
    <h2>Display</h2>
    <div class="d-inline p-2 text-bg-primary">d-inline</div>
    <div class="d-inline p-2 text-bg-dark">d-inline</div>
    <div class="d-none p-2 text-bg-dark">d-inline</div>
  ```
  
  

---

### Bootstrap 컴포넌트

---

- **button**
- **dropdowns**
  - dropdown, dropdown-menu, dropdown-item 클래스를 활용해 옵션 메뉴 만들 수 있음
- **form**
  - form-control 클래스를 활용해 <input> 및 <form> 태그를 스타일링 할 수 있음
- **navbar**
  - 네비게이션 바
- **carousel**
  - 사진, 콘텐츠 순환 시키기 위한 슬라이드 쇼
- **modal**
  - 사용자와 상호작용 하기 위해 사용 / 또 다른 레이어를 띄움
  - 페이지를 이동하면 자연스럽게 사라짐 (제거하지 않고 배경 클릭 시 사라짐) - 팝업과 다른점
  - 트리거의 data-bs-target 과 버튼의 id 를 같은 값으로 연결
  - 중첩해서 넣지 말기 → 탑 레벨에 넣기
- **flexbox**
- **card**
  - Grid card → 화면이 작아지면 1줄에 표시되는 카드 수가 줄어듬

---

### Bootstrap Grid system

---

- 요소들의 디자인과 배치에 도움을 주는 시스템

- flexbox 로 제작 됨

- container, rows, column 으로 컨텐프 배치, 정렬

- 기본 요소
  
  - Column : 실제 컨텐츠를 포함하는 부분
  - Gutter : 칼럼과 칼럼 사이의 공간 (사이 간격)
  - Container : Column들을 담고 있는 공간

- **12개의 column**

- **6개의 grid breakpoints**

- Grid options ex) class=”row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4"
  
  - xs
  - sm
  - md
  - lg
  - xl
  - xxl

---

### Responsive Web Design

---

- 다양한 화면 크기를 가진 디바이스들이 등장하면서 생겨난 개념
- 반응형 웹은 별도의 기술 이름이 아닌 웹 디자인에 대한 접근 방식, 반응형 레이아웃 작성에 도움이 되는 사례들의 모음 등을 기술하는데 사용되는 용어
- 예시)
  - Media Queries, Flexbox, Bootstrap Grid System, The veiwport meta tag
