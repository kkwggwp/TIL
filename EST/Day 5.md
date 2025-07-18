CSS 
======================
## 1. CSS Box model
### 1.1 display 속성
* `block` : 요소 전후에 줄 바꿈 생성
ㄴwidth, height, margin, padding 지정 가능
* `inline` : 요소 전후에 줄 바꿈 생성하지 않는 인라인 요소 상자 생성
ㄴwidth, height 지정 가능
* `inline-block` : 줄 바꿈 없이 한 줄에 놓임
ㄴwidth, height, margin, padding 지정 가능
* `flex` : 내부 자식 요소들의 위치를 부모 컨테이너 요소 안에서 x,y축 단방향(1차원)으로 설정
* `grid` : 내부 자식 요소들의 위치를 부모 컨테이너 요소 안에서 x, y축 모두 이용해(2차원) 설정
* `none` : 접근성 트리에서 해당 요소 제거. 해당 요소 및 하위 요소가 사라지고 스크린리더에도 읽히지 않음

### 1.2 reset CSS
* 브라우저가 기본적으로 제공하는 스타일 때문에 일관된 디자인을 구현하기 위해 사용
* HTML 문서 내에 삽입해도 동작하지만 reset.css 처럼 따로 파일을 두는것을 권장함

## 2. 요소의 배치 CSS position
### 2.1 static
* 속성의 기본값
### 2.2 relative
* 요소를 상대적으로 배치. 다른 콘텐츠들의 위치에 영향을 미치지 않음
### 2.3 absolute
* 요소를 절대적인 위치로 배치
* 가장 가까운 조상 요소중 static이 아닌 값인 요소를 기준으로 함. 아니라면 body 기준
* 다른 요소의 레이아웃에 영향 주지 않음

## 3. 요소 쌓임 맥락
### 3.1 3차원 공간에서의 요소 배치
* 요소들이 겹칠때는 3차원적인 고려 필요

#### 3.1.1 z-index의 기본 특성
* position이 static 외의 값을 가진 박스에 대하여 z축의 위치를 지정
* 값이 클수록 제일 위로 배치됨
* 부모가 z-index를 높여 자식 앞으로 나올 수 없음
* 자식은 z-index를 음수값으로 주어 부모 뒤로 갈 수 있음
* 유지보수를 위해 10이나 100 단위로 작업하면 좋음. 주로 100단위를 많이 사용

#### 3.1.2 쌓임 맥락(Stacking Context)
* position 속성이 없는 요소는 생성 순서에 따라 쌓임
* 가장 나중에 만들어진 요소가 가장 높은 z-index 가짐 이때 부모의 값은 auto
* 이러한 상태의 요소들에 position 속성이 있는 자식이 나타나면 부모의 z-index에 종속되지 않음
* 만약 부모의 z-index 값이 auto가 아닌 정수값(0 ~ n)이라면 부모의 독자적인 stacking-context가 생성되며, 이때부터 자식의 stacking-context는 부모의 stacking-context에 종속적이게 됨

## 4. 요소의 정렬된 배치
### 4.1 flex
* 부모 요소를 `display: flex`로 설정하면 자식 요소들이 `flex item`이 되어 flexbox 레이아웃을 사용할 수 있음
* 부모 요소를 `flex-container` 자식 요소를 `flex-item` 이라고 부름

### 4.2 주 축의 방향
* `row` : 기본값. 왼쪽에서 오른쪽 (주축이 행 방향)
* `column` : 위에서 아래 방향 (주축이 열 방향)
* `row-reverse` : 오른쪽에서 왼쪽
*` column-reverse` : 아래에서 위 방향

### 4.3 주축의 아이템 정렬
* flex-start : 시작점에 정렬
* flex-end : 끝점에 정렬
* center : 가운데 정렬
* space-between : 아이템 사이에 동일한 간격을 설정
* space-around : 아이템 주변에 동일한 간격을 설정
* space-evenly : 아이템 주변과 시작과 끝에 동일한 간격을 설정

### 4.4 align-items
* stretch : 기본값. 교차축을 채우기 위해 아이템을 늘림
* flex-start : 시작점에 정렬
* flex-end : 끝점에 정렬
* center : 가운데 정렬
* baseline : 텍스트의 기준선에 정렬

### 4.5 gap
* 아이템 사이의 간격을 설정

### 4.6 flex-wrap
* 한 줄에 배치되게 할 것인지, 가능한 영역 내에서 여러 행으로 나누어 표현할 것인지 결정

## 5. grid
### 5.1 2차원 레이아웃 grid

그리드 컨테이너 : 그리드의 가장 바깥 영역

그리드 셀 : 그리드의 한 칸 (개념적인 정의) 

그리드 아이템 : 그리드 컨테이너의 자식 요소들 

그리드 트랙 : 그리드의 행(row) 또는 열(column) 

그리드 라인 : 그리드 셀을 구분하는 선

그리드 넘버 : 그리드 라인의 각 번호 

그리드 갭 : 그리드 셀 사이의 간격(gutter) 

그리드 에어리어 : 그리드 셀의 집합 

### 5.1.1 grid 적용법
* 부모 요소에 display: grid를 설정하면 자식 요소들이 grid item이 되어 grid 레이아웃을 사용할 수 있음
* 부모 요소를 grid-container 자식 요소를 grid-item 이라고 부름

### 5.1.2 행 방향과 열 방향 설정
* grid-template-columns는 열방향 그리드 트랙의 사이즈를 설정하고 grid-template-rows 행방향 그리드 트랙의 사이즈를 설정함
* 픽셀, 백분율, fr 단위를 사용할 수 있습니다. fr은 분수(fraction)의 의미로 컨테이너를 분할해줌
