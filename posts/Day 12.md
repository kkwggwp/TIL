프론트엔드 과제와 ChatGPT
======================
ChatGPT 무료 버전을 사용중이며, 이때까지 작성한 코드를 리뷰하고, 구조를 개선해 달라고 말했다</br>
그 결과는 내 코드와 결과물이 완전 같지는 않아서 참고하기는 힘들었지만, 배울점이 있었던것들을 작성하기로 했다

## 1. body와 header

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
        &lt;li class="topmenu-btn"&gt;&lt;a href="index.html"&gt;Home&lt;/a&gt;&lt;/li&gt;
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

.dlbtn {  
  font-weight: 700;
  padding: 15px 31px;  
  border-radius: 40px; 
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



