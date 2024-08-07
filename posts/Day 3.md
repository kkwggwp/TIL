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
1.1 <!DOCTYPE html>
*html living standard 문서 유형 선언

1.2 <html lang="en">
*html 문서의 루트, 최상단 요소
*lang 속성으로 페이지 주 언어 설정

1.3 head
*문서 정보(메타데이터) 를 담음

1.3.1 meta
*데이터를 설명하는 데이터
```
<meta name="description" content="제주 ICT 코딩 컴퓨터학원, 연구원, 출판사" />
```

1.3.2 charset
*문자 인코딩 방식 지정
```
<meta charset="utf-8" />
```
1.3.3 title
*문서 제목 정의

1.3.4 link
*현재 문서와 외부 리소스의 관계 명시
*rel : 대상 파일의 속성
*href : 연결 시 참조할 파일의 위치
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

##2. 기본 문법과 작성
2.1 요소 분석
2.1.1 태그
*<></> 로 구성
2.1.2 요소의 포함
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
2.1.3 빈요소 / 셀프 클로징
*닫는 태그가 없는 요소
*<br>, <img>, <input>등이 있음
```
<br />
<input type="text" />
<img src="" alt="" />
```
2.2 주석
*<!-- 주석 내용 -->
*ctrl + /

##3. Contents 태그
3.1 heading
*<h1>부터 <h6>까지 있고 순서대로 작성 해야함
*숫자가 작을수록 중요도가 높다
3.2 anchor
