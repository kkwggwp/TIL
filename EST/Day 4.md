CSS
======================
## 1. 선택자 기초
### 1.1 전체 선택자 `*`
* 문서 내 모든 요소 선택
* reset.css 파일에서 많이 사용됨
* 강력하지만 페이지 로드 성능에 영향

### 1.2 타입 선택자
* 특정 태그 전체에 스타일을 적용해 너무 일반적으로 사용하면 모든 해당 태그가 동일한 스타일을 가지게됨

### 1.3 아이디 선택자 `#`
* 문서 내에서 한 번만 사용될 수 있음

### 1.4 클래스 선택자 `.`
* 문서 내에서 여러번 사용 가능

### 1.5 특성 선택자`[]`
* 특정 속성을 가진 요소를 선택할 때 사용

### 1.6 그룹 선택자`,`

### 1.7 복합 선택자
### 1.7.1 자손 선택자 ` `
* 특정 요소의 모든 하위요소 선택, 공백으로 구분

### 1.7.2 자식 선택자`>`
* 직계 자식 요소만 선택

### 1.7.3 일반 형제 선택자`~`
* 뒤에 나오는 형제만 선택

### 1.7.4 인접 형제 선택자`+`
* 바로 뒤에 인접한 형제만 선택

## 2. 텍스트 꾸미기
### 2.1 color
### 2.2 font-family
### 2.3 font-size
### 2.4 font-weight
### 2.5 text-align
* left, right, center, justify(양쪽 정렬)
### 2.6 vertical-align
* 블록 레벨 요소에는 적용되지 않음
* baseline, sub, super, top, middle, bottom
### 2.7 line-height
* 행간 조절에는 숫자, 길이, 백분율 사용 가능
* 1.5~2 사이의 값을 사용하면 가독성에 좋음
### 2.8 letter-spacing
* 자간 조절에는 길이 단위, 음수 사용 가능

## 3. 단위
### 3.1 px
* 직관적이나 디바이스별로 다르게 보임
### 3.2 %
* 부모 요소의 크기를 기준
### 3.3 vw, vh (viewport)
* 브라우저 창의 크기를 기준으로 함
### 3.4 em
* 부모 요소로부터 상속받은 요소의 글자 크기를 기준으로 하는 배수 단위
### 3.5 rem (root)
* 최상의 요소의 글자 크기를 기준으로 함 기본 16px
* 기본적으로는 rem으로 사용하고 크기에 따라 조절해야하는 값들은 em으로 사용하자

## 4. 가상 클래스와 가상 요소
### 4.1 가상 클래스 선택자
* `:`을 사용해 표현
### 4.1.1 동적 가상 클래스
* `:hover` : 마우스 포인터가 위에 올라갔을때의 상태 선택
### 4.2.1 구조적 가상 선택자
* `:first-child`, `:last-child`
* body 직계 자손의 경우 `:last-child` 선택자 적용 불가
* `:nth-child()` 유연하여 다양한 패턴 선택 가능

## 4.2 가상 요소
### 4.2.1 요소의 전과 후
* `::before`, `::after` 앞 뒤에 새로운 요소를 추가 가능
* 빈태그 img br input에는 적용 불가

## 5. CSS Box Model
* 웹 페이지 레이아웃의 근간을 이룸
* 모든 HTML 요소는 하나의 박스로 취급되며 이 박스는 콘텐츠, 패딩, 테두리, 마진으로 구성됨
* 처음 레이아웃을 잡을 때 이 박스 모델을 그려보는것이 중요

<img src="/posts/img/CSSbox.png" width="450px" height="300px" alt="CSSbox"></img><br/>
```
1. witdh : 요소 너비 설정. 입력하지 않으면 부모 요소의 너비를 기준으로 계산해 채움
2. height : 요소 높이 설정. 입력하지 않으면 content의 높이만큼만 설정됨
3. padding : 콘텐츠 주변의 여백을 만듬. 작성 순서는 top, rightt, bottom, left 순서
* padding-top 처럼 사용 가능
4. margin : 요소 주변의 여백을 만듬 사용법은 padding과 같음
5. border
* border-width
* border-top-width
* border-right-width
* border-bottom-width
* border-left-width
* border-style
* border-top-style
* border-right-style
* border-bottom-style
* border-left-style
* border-color
* border-top-color
* border-right-color
* border-bottom-color
* border-left-color
6. box-sizing
* 요소의 총 너비와 높이를 계산하는 방식 지정
* content-box : 기본값. width, height에 border, padding 포함하지 않음
* border-box: width, height에 border, padding 포함
* width = 콘텐츠 너비 + border + padding
7. border-radius : 요소의 모서리를 둥글게 만듬
* border-top-left-radius, border-top-right-radius, border-bottom-right-radius, border-bottom-left-radius

```
