프론트엔드 과제와 ChatGPT
======================
ChatGPT 무료 버전을 사용중이며, 이때까지 작성한 코드를 리뷰하고, 구조를 개선해 달라고 말했다
그 결과는 내 코드와 결과물이 완전 같지는 않아서 참고하기는 힘들었지만, 배울점이 있었던것들을 작성하기로 했다

## 1. HTML 구조 개선
```
<header>
      <div id="topmenu">        
        <a href="index.html">
          <img src="./img/Logo-fin.png" alt="HODU"/>
        </a>
        <nav>
          <ul>
            <li class="topmenu-btn"><a href="index.html">Home</a></li>
            <li class="topmenu-btn">About</a></li>
            <li class="topmenu-btn">Support</a></li>
            <li class="topmenu-btn" id="topmenu-dlbtn"><a href="">Download</a></li>
          </ul>
        </nav>
      </div>
    </header>

### 6.1 this
### 6.1.1 전역 범위 호출
```
<table>
  <tr>
    <td>
      <strong>코드 A</strong>
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
        &lt;li class="topmenu-btn" id="topmenu-dlbtn"&gt;&lt;a href=""&gt;Download&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/nav&gt;
  &lt;/div&gt;
&lt;/header&gt;</code></pre>
    </td>
    <td>
      <strong>코드 B</strong>
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
</table>
```
