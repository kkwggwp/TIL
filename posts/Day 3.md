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
## 1.4 body
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
* 위 예제에서 `<section>` 태그는 `<h1>`, `<img>`, `<div>` 태그의 부모 요소
* 위 예제에서 `<h1>`, `<img>`, `<div>` 태그는 `<section>` 태그의 자식 요소
* 위 예제에서 `<h1>`, `<img>`, `<div>` 태그는 서로 형제 관계에 있음
* 위 예제에서 `<strong>` 태그는 `<section>` 태그의 자손 요소

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

## 11. input
### 11.1 input의 속성

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

### 11.2 input의 타입

| 타입       | 설명                                                    |
|------------|---------------------------------------------------------|
| `text`     | 입력한 텍스트를 그대로 표현해주는 `input`             |
| `button`   | 누를 수 있는 간단한 버튼을 만드는 `input`             |
| `password` | 마스크 처리된 텍스트를 입력받는 `input`                |
| `search`   | 검색 창으로 사용할 수 있는 `input`                    |
| `date`     | 날짜를 입력할 때 사용하는 `input`                     |
| `time`     | 시간을 입력할 때 사용하는 `input`                     |
| `range`    | 슬라이드 바 형식의 `input`                             |
| `number`   | 수를 선택할 수 있게 하는 `input`                       |
| `color`    | 색을 선택할 수 있는 `input`                            |
| `radio`    | 선택 항목 중 하나만 선택 가능한 `input`               |
| `checkbox` | 선택 항목 중 0개 이상 선택 가능한 `input`            |
| `file`     | 파일을 업로드할 수 있는 `input`                        |
| `email`    | 이메일 주소를 입력하게 하는 `input`                    |
| `url`      | 웹 페이지 주소를 입력하게 하는 `input`                |
| `tel`      | 전화번호를 입력하게 하는 `input`                       |

## 12. `<label>`
### 12.1 `<label>` 의 사용법
1. 텍스트의 설명과 폼 입력 모드를 포함하는 방식
```
<label>
  이름 :
  <input type="text" name="name" />
</label>
```
2. 폼 입력에서 분리하여 `for` 속성을 이용해 레이블을 지정하는 방식
```
<label for="myName">이름 : </label>
<input type="text" name="name" id="myName" />
```

### 12.2 `for` 속성
*레이블이 속한 `input`과 같은 폼 컨트롤을 의미

## 13. `<select>`
* 드롭다운 리스트 박스 생성. 박스 안의 아이템은 `<option>` 사용
```
<form action="">
  <label for="myDevice"
    >현재 사용하고 있는 스마트폰의 제조사를 선택해주세요</label
  >
  <select name="device" id="myDevice">
    <option value="iphone">아이폰</option>
    <option value="galaxy">갤럭시폰</option>
    <option value="ㅜㅜ">LG폰</option>
  </select>
</form>
```
### 13.1 `<select>`의 속성들
* `multiple="multiple"` : 여러 개의 옵션을 선택할 수 있게 함 (Windows: Ctrl 클릭, macOS: Command 클릭)
* `size` : 드롭다운 리스트에서 한 번에 보여줄 옵션의 개수를 조절

### 13.2 `<option>`의 속성들
* `value` : 선택된 옵션의 값을 서버에 전송할 때 사용됩
* * `selected` : 기본적으로 선택되는 옵션을 지정 `selected` 속성이 없으면 첫 번째 옵션이 기본적으로 선택됨

## 14. `<fieldset>`
* 폼 컨트롤을 그룹화하여 섹션별로 나눌 때 사용됨
```
<!-- 브라우저에서 어떻게 표현되는지 확인해보세요 -->
<form action="">
  <fieldset>
    <legend>개인정보</legend>
    <label for="myName">이름</label>
    <input type="text" name="name" id="myName" />
    <label for="myTel">전화번호</label>
    <input type="tel" name="tel" id="myTel" />
    <label for="myEmail">이메일</label>
    <input type="email" name="email" id="myEmail" />
  </fieldset>
  <fieldset>
    <legend>개인정보 제공 동의</legend>
    <label for="checkAgree">개인정보 제공에 동의하십니까?</label>
    <input type="checkbox" name="agree" id="checkAgree" />
  </fieldset>
</form>
```
## 15. `<legend>`
* `<fieldset>`의 첫 번째 자식 요소로, 폼 그룹의 제목을 나타냄

## 16. `<button>`
* 클릭 가능한 버튼을 생성합니다. 버튼의 `type` 속성에 따라 다음과 같은 기능을 제공
* `submit` : 폼 데이터를 서버로 제출
* `reset` : 폼의 모든 값을 초기화
* `button` : 클릭 가능한 버튼
* `button`은 `input` 보다 스타일 적용하기 훨씬 수월함

## 17. `<textarea>`
* 여러 줄의 텍스트를 입력받을 수 있음
* `cols` : 입력창의 넓이를 지정
* `rows` : 입력 창에서 보여줄 줄 수를 지정
```
<textarea
  name=""
  id=""
  cols="40"
  rows="10"
  maxlength="10"
  minlength="5"
></textarea>
```

## 18. `<datalist>`
* `<input>`의 `list` 속성과 연결하여 사용하며, 기본 선택 옵션을 제공하고 사용자에게 임의의 값을 입력받을 수 있게 함

## 19. HTML CheatSheet
| 태그 이름         | 설명                                       | 구분           | 대표 속성                                     |
|-------------------|------------------------------------------|----------------|----------------------------------------------|
| `<html> </html>`  | HTML 문서를 만들 때 사용                    | 기본 태그      |                                              |
| `<head> </head>`  | 제목이나 표시되지 않는 정보를 설정           | 기본 태그      |                                              |
| `<body> </body>`  | 문서의 보이는 부분을 설정                   | 기본 태그      | bgcolor, link, text, vlink, alink            |
| `<title> </title>`| 제목 표시줄에 들어가는 내용을 설정           | 기본 태그      |                                              |
| `<pre> </pre>`    | 텍스트를 있는 그대로 출력                   | 글자태그       |                                              |
| `<h1> </h1> ... <h6> </h6>` | 제목 텍스트 설정. 숫자가 작아질수록 크기가 커짐 | 글자태그       |                                              |
| `<b> </b>`        | 텍스트를 볼드체로 만드는데 사용               | 글자태그       |                                              |
| `<i> </i>`        | 이탤릭체 텍스트를 만드는데 사용               | 글자태그       |                                              |
| `<tt> </tt>`      | 타자기 스타일의 텍스트를 만드는데 사용        | 글자태그       |                                              |
| `<code> </code>`  | 모노스페이스인 소스코드를 정의하는데 사용      | 글자태그       |                                              |
| `<cite> </cite>`  | 인용문을 표시하는데 사용                     | 글자태그       |                                              |
| `<adress> </adress>` | 주소를 표시하는데 사용                    | 글자태그       |                                              |
| `<em> </em>`      | 텍스트를 이탤릭체로 강조하는데 사용           | 글자태그       |                                              |
| `<strong> </strong>` | 볼드 텍스트를 만드는데 사용                | 글자태그       |                                              |
| `<font> </font>`  | 폰트의 크기 색상 등을 설정하는데 사용          | 글자태그       | size, color, face                            |
| `<a>`             | 링크를 연결할 때 사용                      | 링크태그       | href, name, target                           |
| `<p> </p>`        | 새 단락을 만들 때 사용                      | 컨텐츠 그룹 태그 |                                              |
| `<br>`            | 줄바꿈을 넣을 때 사용                       | 컨텐츠 그룹 태그 |                                              |
| `<blockquote> </blockquote>` | 들여쓰기를 통해서 인용문을 만들 때 사용   | 컨텐츠 그룹 태그 |                                              |
| `<div> </div>`    | CSS로 블록 컨텐츠를 형식화 하는데 사용         | 컨텐츠 그룹 태그 |                                              |
| `<span> </span>`  | CSS로 인라인 컨텐츠를 형식화 하는데 사용      | 컨텐츠 그룹 태그 |                                              |
| `<ul> </ul>`      | 순서가 없는 리스트를 만듭니다                | 컨텐츠 그룹 태그 |                                              |
| `<ol> </ol>`      | 순서가 있는 리스트를 만듭니다                | 컨텐츠 그룹 태그 | start, type                                   |
| `<li> </li>`      | 각 리스트의 항목들을 포함합니다              | 컨텐츠 그룹 태그 |                                              |
| `<dl> </dl>`      | 정의 목록들을 만듭니다                      | 컨텐츠 그룹 태그 |                                              |
| `<dt> </dt>`      | 정의되는 용어의 제목을 만듭니다              | 컨텐츠 그룹 태그 |                                              |
| `<dd> </dd>`      | 정의되는 용어의 설명을 만듭니다              | 컨텐츠 그룹 태그 |                                              |
| `<hr>`            | 수평선을 삽입합니다                         | 미디어태그     | size, width, noshade                         |
| `<img>`           | 이미지를 표시할 때 사용                     | 미디어태그     | src, width, height                           |
| `<form> </form>`  | 폼을 정의하는데 사용                        | 폼 태그        | src, align, border, height, width, src       |
| `<select> </select>` | 다양한 메뉴 형태를 만드는데 사용            | 폼 태그        | multiple, name, size                         |
| `<option> </option>` | 각 메뉴 항목들을 배치하는데 사용            | 폼 태그        |                                              |
| `<textarea> </textarea>` | 텍스트 박스 영역을 만드는데 사용           | 폼 태그        | name, cols, rows                             |
| `<input>`         | 다양한 입력 양식을 만드는데 사용            | 폼 태그        | type, name, value, checked                   |
| `<table> </table>` | 표를 만드는데 사용                           | 테이블 태그    | border, cellpadding, cellspacing, width       |
| `<tr> </tr>`      | 표의 행들을 배치하는데 사용                  | 테이블 태그    | align, valign                                |
| `<td> </td>`      | 표의 각 셀들을 배치하는데 사용                | 테이블 태그    | align, valign, rowspan, colspan, nowrap      |
| `<th> </th>`      | 테이블 헤더를 배치하는데 사용                 | 테이블 태그    |                                              |
