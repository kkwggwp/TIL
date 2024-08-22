프론트엔드 과제와 ChatGPT
======================
ChatGPT 무료 버전을 사용중이며, 이때까지 작성한 코드를 리뷰하고 구조를 개선해 달라고 말했다</br>
개선해준 코드는 내 코드와 결과물이 완전 같지는 않아서 100% 참고하기는 힘들었지만 배울점이 있었던것들을 작성하기로 했다

A가 내 코드, B가 ChatGPT가 다듬은 코드

<table>
  <tr>
    <td>
      <strong>HTML A</strong>
      <pre><code>&lt;header&gt;
  &lt;div id="topmenu"&gt;        
    &lt;a href="index.html"&gt;
      &lt;img src="./img/Logo-fin.png" alt="HODU"/&gt;
    &lt;/a&gt;
    &lt;nav&gt;
      &lt;ul&gt;
        &lt;li class="topmenu-btn"&gt;&lt;a href="index.html"&gt;Home
        &lt;/a&gt;&lt;/li&gt;
        &lt;li class="topmenu-btn"&gt;About&lt;/a&gt;&lt;/li&gt;
        &lt;li class="topmenu-btn"&gt;Support&lt;/a&gt;&lt;/li&gt;
        &lt;li class="topmenu-btn" id="topmenu-dlbtn"&gt;
        &lt;a href=""&gt;Download&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/nav&gt;
  &lt;/div&gt;
&lt;/header&gt;</code></pre>
    </td>
    <td>
      <strong>HTML B</strong>
      <pre><code>&lt;header&gt;
  &lt;div id="topmenu"&gt;
    &lt;a href="index.html"&gt;&lt;img src="./img/Logo-fin.png" alt="HODU Logo"&gt;&lt;/a&gt;
    &lt;nav&gt;
      &lt;ul&gt;
        &lt;li&gt;&lt;a href="index.html"&gt;Home&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#"&gt;About&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#"&gt;Support&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#" id="topmenu-dlbtn"&gt;Download&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/nav&gt;
  &lt;/div&gt;
&lt;/header&gt;</code></pre>
    </td>
  </tr>
  <tr>
    <td>
      <strong>CSS A</strong>
      <pre><code>body {  
  font-family: Pretendard, sans-serif;
  font-size: 1rem;
  font-weight: 400;
  line-height: 20px;
  width: 100%;
  margin: 0 auto;  
}

header {
  background-color: #f2e9d8;
}

nav,
ul {
  display: flex;
  align-items: center;
}

#topmenu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  box-sizing: border-box;  
  width: 66.67%;
  height: 102px;
  margin: 0 auto;
}

.topmenu-btn {
  list-style-type: none;
  margin-left: 30px;
}

#topmenu-dlbtn {
  font-weight: 700;
  padding: 15px 31px;  
  border-radius: 40px;
  margin-left: 49px;
  width: 140px;
  box-sizing: border-box; 
  color: #fff;
  background-color: #d97652;   
}

</code></pre>
    </td>
    <td>
      <strong>CSS B</strong>
      <pre><code>body {
  font-family: Pretendard, sans-serif;
  font-size: 1rem;
  line-height: 1.25;
  margin: 0;
  padding: 0;
}

header, footer {
  background-color: #f2e9d8;
  padding: 1rem 0;
}

#topmenu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

#topmenu img {
  height: auto;
}

nav ul {
  display: flex;
  gap: 1.5rem;
  list-style: none;
}

nav a {
  text-decoration: none;
  color: #000;
}

#topmenu-dlbtn {
  font-weight: 700;
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  background-color: #d97652;
  color: #fff;
}
</code></pre>
    </td>
  </tr>
</table>

##1. HTML 구조
  * li에 class를 줬던 나와는 다르게 nav ul {} 로 관리해서 HTML 코드가 보기 더 깔끔해졌다 나도 nav ul{}써놓고 왜 생각을 못했을까
  * 어차피 동작하지 않을 버튼들에는 a 태그를 주지 않았던 나와 다르게 다 삽입되어있다

##2. body CSS
  * body에서 width: 100%;, topmenu에서 width: 66.67%와 topmenu에서 max-width: 1200px를 준 차이가 보인다
  * 결국 뭐가 더 좋은지 모르겠어서 찾아봤더니 각각의 장점이 있고 정리하자면 body는 100% 주고 컨테이너등에서는 max-width를 적용하는게 좋다고 하는듯 하다
  * font-weight는 노멀이 400이었다 작성할 필요 없었던 것
  * line-height는 px단위보다 배수를 사용하는게 반응형 디자인에 유리함
  
##3. topmenu-btn, nav ul, nav a
  * nav ul에 margin 대신 gap과 rem을 사용했다
  * border-box는 필요없었다
  * text-decoration: none;을 이용해 하이퍼링크 특유의 파란글씨와 밑줄을 없앴다

##4. dlbtn
  * 전체적으로 피그마와는 멀어진 값들이라 내 값을 rem으로 변환하는 정도만 하면 좋을듯 하다
  * 마찬가지로 border-box는 필요없었고, margin-left는 피그마처럼 하기에는 유지하는게 좋겠다

##5. topmenu
  * height를 주지 않은 모습을 따라하려고 했으나 피그마처럼 구현하기는 힘들어서 height값을 주는 방향으로 가기로 했다

이 이후로도 다듬을 것들이 있지만 비슷한 이유거나 단순 rem 변환등이라 생략하겠다</br>
폰트 스타일링이라던지 이미지 크기나 배치등은 전혀 고려를 하지 않은 부분들이 있었다 </br>
따라서 무료 ChatGPT로 더 효율 좋게 만들어달라는 주문을 하는것 보다는 </br>
그냥 코드를 어떻게 하면 더 보기 좋게 또는 효율 좋게 만드는지 구체적으로 물어보는게 더 도움이 될 것 같다</br>
