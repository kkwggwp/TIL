HTML/CSS
======================
## 1. HTML

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

### 1.1 `<!DOCTYPE html>`
* html living standard 문서 유형 선언

### 1.2 `<html lang="en">`
* html 문서의 루트, 최상단 요소
* lang 속성으로 페이지 주 언어 설정

### 1.3 head
* 문서 정보(메타데이터) 를 담음

#### 1.3.1 meta
* 데이터를 설명하는 데이터

```
<meta name="description" content="제주 ICT 코딩 컴퓨터학원, 연구원, 출판사" />
```

### 1.3.2 charset
* 문자 인코딩 방식 지정

```
<meta charset="utf-8" />
```

### 1.3.3 title
* 문서 제목 정의

### 1.3.4 link
* 현재 문서와 외부 리소스의 관계 명시
* rel : 대상 파일의 속성
* href : 연결 시 참조할 파일의 위치

```
<html>
  <head>
    <!-- 스타일 시트 링크 -->
    <link rel="stylesheet" href="style.css" />
 
    <!-- 폰트 링크 -->
    <link rel="stylesheet" href="font.ttf" />
 
    <!-- 파비콘 링크 -->
    <link rel="shortcut icon" href="favicon.ico" />
  </head>
  <body></body>
</html>
```
1.4 body
*웹 페이지의 실제 내용

## 2. 기본 문법과 작성

### 2.1 요소 분석
#### 2.1.1 태그
* `<></>` 로 구성
#### 2.1.2 요소의 포함

```
<p>
  HTML은 요소 안에
  <strong>다른 요소</strong>가 들어갈 수 있습니다
</p>
 
<!-- 잘못 사용된 예 -->
<p>
  HTML은 요소 안에
  <strong>다른 요소 가 들어갈 수 있습니다
</p>
  </strong>
```

#### 2.1.3 빈요소 / 셀프 클로징
* 닫는 태그가 없는 요소
* `<br>, <img>, <input>`등이 있음
* 
```
<br />
<input type="text" />
<img src="" alt="" />
```

### 2.2 주석
* <!-- 주석 내용 -->
* ctrl + /

## 3. Contents 태그

### 3.1 heading
* `<h1> ~ <h6>`까지 있고 순서대로 작성 해야함
* 숫자가 작을수록 중요도가 높다

### 3.2 anchor
* 다양한 URL로 연결할 수 있는 하이퍼링크 작성
* _self 현재 페이지에서 링크 열기(기본값)
* _blank 새 탭에서 링크 열기
* download 링크 클릭시 URL 다운로드 요청

### 3.3 paragraph
* 문단 정의시 사용
* `<p>`
* p태그 안에 다른 p태그 등의 블록 요소를 넣는것은 올바른 방법이 아님

### 3.4 strong
* 텍스트의 중요성 강조
* 비슷한 태그로는 `<b>`가 있음 시각적 강조로 사용
* 스크린 리더 활용시 거센 억양으로 소리냄

### 3.5 br & hr
*각각 줄 바꿈과 수평선을 나타냄
*호완성, 가독성, 안정성을 위해 `</br>` 사용 권장

### 3.6 pre
* 사전 텍스트 정의할 때 사용
* 텍스트의 공백과 서식을 유지해야 할 때 사용

## 4. 목록 태그
### 4.1 ol
* 순서가 있는 목록에 사용
* 자식으로는 `li` 태그만 사용 가능

### 4.2 ul
* 순서가 없는 목록에 사용
* 자식으로는 `li`태그만 사용 가능

### 4.3 li
* `ol`과 `ul`의 자식으로만 사용 가능
* 같은 위상의 아이템이어야 함

### 4.4 중첩 사용
```
<ul>
  <li>A</li>
  <li>B</li>
  <li>C</li>
  <li>D</li>
  <li>
    E
    <ol>
      <li>가</li>
      <li>나</li>
      <li>다</li>
    </ol>
  </li>
</ul>
```

## 5. Media와 div & span 태그
### 5.1 img
* 이미지 삽입용
* 닫는 태그 없음
* src : 경로 지정
* alt : 대체 텍스트, 이미지에 대한 설명(스크린 리더 지원)
```
<img src="image.jpg" alt="이미지" />
```

#### 5.1.1 상대경로
* `./` 현재 폴더
* `../` 상위 폴더
* .`/폴더명/` 하위 폴더

#### 5.1.2 절대경로
* 최상위 디렉토리부터 전체 경로로 나타낸 것

#### 5.1.3 파일 및 폴더 이름 규칙
* 공백 없이 영문 소문자, - 사용 권장

### 5.2 div % span
#### 5.2.1 div
* 웹 페이지의 레이아웃을 구성하기 위한 태그
* 블록 요소로 개행이 되면 여러 태그를 그룹핑 하기 위한 용도
* CSS로 스타일 주기 전에는 영향 X
* div 대신 사용 할 수 있는 시멘틱한 태그들이 있어 그 쪽을 사용 권장함

#### 5.2.2 span
* 인라인 요소로 사용
* CSS로 스타일 주기 전에는 영향 X
* 텍스트의 일부분에 스타일 적용시 사용
* 텍스트의 일부분에 JavaScript 이벤트 적용시 사용

```
<p>
  위니브는 <span>라이캣</span>과 <span>로지</span>와 <span>지지</span>가
  있습니다.
</p>
```

## 6. Sections 태그
### 6.1 header
* 웹 페이지의 상단에 위치하며 사이트의 제목, 로고, 검색창, 네비게이션 등의 요소 포함
* `<head>`는 문서의 메타데이터를 포함하나 `<header>`는 문서의 내용 중 소개 부분을 나타냄
* 중첩 사용 불가, `<footer>` 포함 가능
* 각 섹션의 시작 부분에 사용해 해당 섹션의 소개 부분을 나타낼 수 있음

### 6.2 nav
* 현재 또는 다른 페이지로 이동 할 수 있는 링크들을 모아 둔 섹션. 메뉴 목차, 브레드크럼 등으로 사용
* 메뉴로 사용시 `<ul>`과 함께 사용하면 좋음

### 6.3 main
* 문서의 주요 콘텐츠. 한 번만 사용가능

### 6.4 footer
* 웹 페이지의 하단에 위치. 페이지의 작성자, 저작권, 관련 문서 등의 내용을 담음
```
<footer>
  <h2>
    <span class="a11y-hidden">wenivooks</span>
  </h2>
  <p>Copyright © 2023 WENIV All Rights Reserved</p>
  <!-- 생략... -->
</footer>
```

### 6.5 section
* 문서 내에서 특정한 섹션 정의시 사용. 주제나 컨텐츠를 구분짓기 위함
* 뉴스의 사회면/연예면 등으로 사용
* 자식요소로 heading을 포함해야 함

### 6.6 article
* 독립적으로 구분해 배포하거나 재사용가능한 구획을 나타냄. 독립적인 기능 수행
* 뉴스 홈페이지 처럼 다양한 기사에 사용됨
* `<section>`은 주제별로 구분하고 `<article>`은 독립적인 콘텐츠를 구분함
* 게시판, 블로그 글, 매거진, 뉴스 기사, 위젯, 실시간 채팅창에 사용
* 자식요소로 heading을 포함해야 함

### 6.7 aside
* 문서의 주요 내용과 간접적으로 연관된 부분을 나타냄
* 사이드바, 광고, 관련 링크, 삽화 등을 표시

## 7. Forms & Tables 태그
### 7.1 Forms
* 폼은 웹 페이지에서 사용자로부터 데이터를 수집하고 서버로 전송하는 데 사용됨
* 로그인, 회원 가입, 검색, 설문조사 등 다양한 기능을 구현할 때 사용

#### 7.1.1 `<form>` 태그
* 폼을 정의하는 컨테이너
* action 속성: 데이터를 처리할 서버의 URL을 지정
* method 속성: 데이터 전송 방식을 설정함 (GET, POST 등)
html
```
<form action="/login" method="POST">
  <!-- 폼 요소들 -->
</form>
```
### 7.2 `<input>` 태그
* 사용자 입력을 받는 기본 요소
* type 속성 : 입력 필드의 유형을 정의 (text, password, checkbox, radio 등)
* name 속성: 폼 데이터와 함께 전송되는 필드의 이름을 설정
* id 속성: 레이블과 연결할 때 사용됩니다.
```
<input type="text" id="username" name="username" />
<input type="password" id="password" name="password" />
```
### 7.3 `<label>` 태그
* 입력 필드의 설명을 제공
* for 속성: 레이블이 설명하는 입력 요소의 ID를 지정
```
<label for="username">아이디:</label>
<input type="text" id="username" name="username" />
```

로그인 폼을 구현하는 예제
------
```
<form action="/login" method="POST">
  <label for="username">아이디:</label>
  <input type="text" id="username" name="username" />
  <label for="password">비밀번호:</label>
  <input type="password" id="password" name="password" />
  <button type="submit">로그인</button>
</form>
```
## 8. Tables 
* 테이블은 정보를 행과 열로 구조화하여 표시
* `<table>` 태그: 테이블을 정의
* `<tr>` 태그: 테이블의 행을 정의
* `<th>` 태그: 테이블의 헤더 셀을 정의 기본적으로 굵은 글씨와 가운데 정렬됨
* `<td>` 태그: 테이블의 데이터 셀을 정의합
```
<table>
  <tr>
    <th>제품명</th>
    <th>가격</th>
    <th>수량</th>
  </tr>
  <tr>
    <td>노트북</td>
    <td>100만원</td>
    <td>10</td>
  </tr>
  <tr>
    <td>스마트폰</td>
    <td>80만원</td>
    <td>20</td>
  </tr>
  <tr>
    <td>태블릿</td>
    <td>60만원</td>
    <td>15</td>
  </tr>
</table>
```

## 9. 태그의 관계
* HTML문서는 트리 형태로 이루어져 있고 각 요소들은 부모-자식, 형제 관계를 가짐
```
<html>
  <head></head>
  <body>
    <section>
      <h1>
        <strong></strong>
      </h1>
      <img />
      <div>
        <p><strong></strong></p>
        <p><strong></strong></p>
        <p><strong></strong></p>
      </div>
    </section>
  </body>
</html>
```
### 9.1 Parent, Child, Sibling, Descendant 요소
* 위 예제에서 <section> 태그는 <h1>, <img>, <div> 태그의 부모 요소
* 위 예제에서 <h1>, <img>, <div> 태그는 <section> 태그의 자식 요소
* 위 예제에서 <h1>, <img>, <div> 태그는 서로 형제 관계에 있음
* 위 예제에서 <strong> 태그는 <section> 태그의 자손 요소

## 10. Forms
### 10.1 기본 속성
- **폼(Form)**: 정보를 입력하고 제출하는 영역.
- **속성**:
  - `action`: 데이터를 전송할 페이지의 URL.
  - `method`: 데이터 전송 방법. (`get` 또는 `post`)

### 10.1 폼 동작 방식
  1. 사용자가 웹 페이지의 폼에 데이터를 입력합니다.
  2. 폼이 제출되면 데이터는 웹 서버로 전송됨
  3. 웹 서버는 데이터 처리를 위해 APP 호출
  4. 필요 시, APP은 DB로 데이터를 전송
  5. DB에서 CRUD 작업을 수행하고 결과를 애플리케이션과 웹 서버로 전송
  6. 웹 서버는 결과를 Client로 보냄
  7. 브라우저는 Response 받은 페이지를 렌더링함

### 10.2
* action : 입력 값을 전송할 페이지를 나타냄
* method : 폼의 데이터를 전송할 방법 정의

### 11. input

| 속성명       | 설명                                                        |
|--------------|-------------------------------------------------------------|
| `type`       | 태그 모양을 다양하게 변경할 수 있습니다. 예: `text`, `radio`, `checkbox`, `password`, `button` 등. |
| `name`       | 태그 이름을 지정합니다.                                     |
| `readonly`   | 태그를 읽기 전용으로 설정합니다.                             |
| `maxlength`  | 입력할 수 있는 최대 글자 수를 지정합니다.                    |
| `minlength`  | 입력해야 하는 최소 글자 수를 지정합니다.                    |
| `required`   | 필수 입력 필드로 설정합니다. 값을 입력하지 않고 submit 버튼을 누르면 에러가 발생하고 데이터가 전송되지 않습니다. |
| `autofocus`  | 웹 페이지 로딩 시 이 속성이 지정된 태그로 자동으로 포커스가 이동합니다. |
| `placeholder`| 입력할 값에 대한 힌트를 제공합니다.                         |
| `pattern`    | 정규표현식을 사용하여 특정 범위 내의 유효한 값을 입력 받도록 합니다. |
