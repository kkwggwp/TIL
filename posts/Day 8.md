JAVASCRIPT
======================
## 6. 조금 더 깊이 들여다 보기
### 6.1 this
### 6.1.1 전역 범위 호출
```
console.log(this);
```
* 전역 범위에서 this는 전역 객체이다
* 브라우저단에서는 `window`, Node.js 환경에서는 `global` 이 전역 객체
```
console.log(this); // window
window.alert('hello');
this.alert('hello');
```
### 6.1.2 함수 범위 호출
```
// 1. 일반 함수 호출
function f() {
    console.log(this); // window
}
f();
// 2. 화살표 함수 호출
const obj = {
  f: function () {
    const ff = () => {
      console.log(this);
    };
    ff();
 
    const fff = function () {
      console.log(this);
    };
    fff();
  },
};
 
obj.f();
// f (화살표 함수 ff에서의 this)
// Window 객체 (일반 함수 fff에서의 this)

// 3. 메서드 호출
const obj = {
    name: 'licat',
    f: function () {
        console.log(this);
    },
};

obj.f(); // obj
// 4. 생성자 함수 호출
function Person(name) {
    this.name = name;
    this.age = 1;
    console.log(this);
    // return this
}

const person1 = new Person('licat'); 
// Person { name: "licat" }
const person2 = new Person('mura');
// Person { name: "mura" }
```
### 6.1.3 이벤트 핸들러 내에서 호출
* 이벤트 핸들러는 사용자나 브라우저의 특정 동작에 반응하여 실행되는 함수(핸들러 함수)
```
<button id="btn">hello world!</button>
const button = document.getElementById('btn');
button.addEventListener('click', (function() {
    console.log(this); // <button id="btn">Click me!</button>
}));
// 이벤트 핸들러는 실무에서 this를 많이 사용함
<!DOCTYPE html>
<html>
<body>
<input type="checkbox" id="checkbox" /> 체크해보세요.
<script>
    const checkbox = document.getElementById('checkbox');
    checkbox.addEventListener('change', function () {
        if (this.checked) {
            document.body.style.backgroundColor = 'lightblue';
        } else {
            document.body.style.backgroundColor = '';
        }
    });
</script>
</body>
</html>
```
### 6.2 반복문
### 6.2.1 for in
* 객체의 속성(키)을 순회하는데 사용. 각 반복 단계에서 객체의 키가 변수에 할당됨
```
const arr = [10, 20, 30, 40, 50];
const obj = {a: 1, b: 2, c: 3, d: 4, e: 5};

for (let key in obj) {
    console.log(key, obj[key]);
}

for (let key in arr) {
    console.log(key, arr[key]);
}
// for in은 배열을 순회할때 사용하기 적합하지 않다 forEach 메서드 사용이 권장됨
// 속성을 순회할때 사용하자
```
### 6.2.2 for of
* iterable (배열, 문자열, Map, Set) 객체의 값을 순회하는데 사용됨
*
```
const arr = [10, 20, 30, 40, 50];
const obj = {a: 1, b: 2, c: 3, d: 4, e: 5};

for (let value of arr) {
    console.log(value);
}

for (let value of Object.values(obj)) {
    console.log(value);
}


let data = [
    {
        "지역이름": "전국",
        "확진자수": 24889,
        "격리해제수": 23030,
        "사망자수": 438,
        "십만명당발생율": 48.0,
        "지역별확진자비율": ""
    },
    {
        "지역이름": "서울",
        "확진자수": 5607,
        "격리해제수": 5050,
        "사망자수": 66,
        "십만명당발생율": 57.61,
        "지역별확진자비율": 22.53
    },
    {
        "지역이름": "부산",
        "확진자수": 491,
        "격리해제수": 423,
        "사망자수": 4,
        "십만명당발생율": 14.39,
        "지역별확진자비율": 1.97
    },
    {
        "지역이름": "대구",
        "확진자수": 7141,
        "격리해제수": 6933,
        "사망자수": 196,
        "십만명당발생율": 293.09,
        "지역별확진자비율": 28.69
    }
];

for (let d of data) {
    console.log(d['지역이름'], d['확진자수'], d['격리해제수'], d['사망자수'], d['십만명당발생율'], d['지역별확진자비율']);
}

for (let i = 0; i < data.length; i++) {
    console.log(data[i]['지역이름'], data[i]['확진자수'], data[i]['격리해제수'], data[i]['사망자수'], data[i]['십만명당발생율'], data[i]['지역별확진자비율']);
}

// for in은 키 순회
// for of는 객체의 값 순회
// object는 iterable이 아니기 때문에 for of가 불가
```
### 6.3 Map과 Set
### 6.3.1 Map
* 키-값 쌍을 저장할 수 있는 구조
* 값을 추가할때는 `set` 메서드 사용
* 값을 가져올때는 `get` 메서드 사용
* 값을 확인할때는 `has` 메서드 사용
* 값을 제거할때는 `delete` 메서드 사용
* 크기를 확인할때는 `size` 속성 사용
* 모든 데이터 할때는 `clear` 메서드 사용
* for of 반복문 사용해 키와 값에 접근
* 키와 값에 각각 접근할 때는 `keys`와 `values` 메서드를 사용
* 배열을 Map으로 변환하거나, 그 반대로 변환할 수 있음
* Map은 데이터를 추가하거나 제거하는 작업에서 Object보다 성능이 좋음
```
// Map
// key, value로 이루어진 데이터를 저장할 때 사용
// 어떠한 언어도 이렇게 비슷한 자료형을 가지고 있는 경우는 없습니다.
// let m = new Map();
// console.log(m); // Map(0) {}

let m = new Map();

m.set('하나', '1');
m.set(1, '하나');
m.set(true, 1);
m.set(false, 0);

console.log(m);
console.log(m.get('하나')); // '1'
console.log(m.get(true)); // 1

// in 연산자
console.log('하나' in {'하나': '1', '둘': '2'}); // true
// map에서는 has 메서드를 사용합니다.
console.log(m.has('하나')); // true

console.log(m.delete('하나')); // true
console.log(m.has('하나')); // false
console.log(m.size); // 2

const data = new Map().set('name', 'licat').set('age', 10).set('height', 180);

for (const value of data) {
    console.log(value[0]);
    console.log(value[1]);
}

for (const [key, value] of data) {
    console.log(key);
    console.log(value);
}

console.log([...data.keys()]);
console.log([...data.values()]);

// 배열을 Map으로 변환
let temp = new Map([
    [1, 10],
    [2, 20],
    [3, 30],
    [4, 40],
]);

// 객체를 Map으로 변환
let temp2 = new Map(Object.entries({ one: 1, two: 2 }));
```

### 6.3.2 Set
* 중복되지 않는 값들의 집합을 저장할 수 있는 구조
* 값을 추가할때는 `add` 메서드 사용
* 값을 확인할때는 `has` 메서드 사용
* 값을 제거할때는 `delete` 메서드 사용
* 크기를 확인할때는 `size` 속성 사용
* 모든 데이터 할때는 `clear` 메서드 사용
* for of 반복문 사용해 값에 접근
* 배열을 Set으로 변환하거나, 그 반대로 변환할 수 있음
```
// Set
// 중복을 허락하지 않는 자료형
// 중복하지 않는 데이터를 저장할 때 사용
// 중복을 제거하는 용도로도 사용

// let s = new Set();
// console.log(s); // Set(0) {}

let s = new Set();

s.add(10);
s.add(20);
s.add(30);
s.add(30); // 중복된 값은 추가되지 않습니다.
s.add(30);

console.log(s);

let ss = new Set('abcdeeeeeeeee');
console.log(ss);
console.log(ss.size);


let sss = new Set([10, 20, 30, 10, 20, 30, 30]);
console.log(sss);
console.log(sss.size);
console.log(sss.has(10));

console.log(sss.delete(10));
console.log(sss.has(10));

let s2 = new Set(['apple', 'banana', 'orange']);

for (let value of s2) {
  console.log(value);
}

let setA = new Set(['apple', 'banana', 'orange']);
let setB = new Set(['banana', 'kiwi', 'orange']);

// 교집합
let intersection = new Set([...setA].filter(x => setB.has(x)));
console.log(intersection); // Set(2) {"banana", "orange"}

// 합집합
let union = new Set([...setA, ...setB]);
console.log(union); // Set(4) {"apple", "banana", "orange", "kiwi"}

// 차집합
let difference = new Set([...setA].filter(x => !setB.has(x)));
console.log(difference); // Set(1) {"apple"}

////////////////////////////////////////////

// array에 filter와 reduce
// filter는 안에 들어간 함수가 true를 리턴하는 요소만 모아서 새로운 배열을 만듭니다.
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
arr.filter(x => x % 2 === 0);

// reduce는 배열의 각 요소를 연산합니다.
let arr2 = [1, 2, 3, 4, 5];
arr2.reduce((a, c) => a + c, 0); // a는 누적값(accumulator), c는 현재(current value)
// 0이 없으면 비어있는 배열일때 애러가 납니다.
```
### 6.4 JSON
* 데이터를 저장하고 전송하는 데 사용되는 가벼운 텍스트 기반의 데이터 교환 형식
* 자바스크립트 객체 표기법을 기반으로 하지만 언어에 독립적이어서 다양한 프로그래밍 언어에서 사용됨
* JSON은 이름과 값의 쌍으로 이루어진 데이터 객체를 표현합니다
* 이름과 값은 콜론(:)으로 구분
* 데이터 객체는 쉼표(,)로 구분
* 데이터 객체는 중괄호({})로 묶어서 표현
* 배열은 대괄호([])로 묶어서 표현
```
// JSON
// JavaScript Object Notation
// 주로 통신에서 많이 사용됩니다. 가벼운 텍스트 데이터를 교환하는데 사용합니다.
// 항상 중괄호로 시작하는 것은 아니고 대괄호나 중괄호로 시작할 수 있습니다.

const data = {
    "name": "licat",
    "age": 25,
    "hobby": ["낚시", "독서", "등산", "요리"],
    "relationship": {
        "friend": ["뮤라", "빙키", "개리"],
        "enemy": ["라이언"]
    }
}

console.log(data["hobby"][0]);

// JSON
// {
//   "squadName": "슈퍼히어로",
//   "members": [
//     {
//       "name": "아이언맨",
//       "age": 29,
//       "본명": "토니 스타크"
//     },
//     {
//       "name": "헐크",
//       "age": 39,
//       "본명": "부르스 배너"
//     }
//   ]
// }


//XML
// <?xml version="1.0" encoding="UTF-8" ?>
// <root>
//   <squadName>슈퍼히어로</squadName>
//   <members>
//     <name>아이언맨</name>
//     <age>29</age>
//     <본명>토니 스타크</본명>
//   </members>
//   <members>
//     <name>헐크</name>
//     <age>39</age>
//     <본명>부르스 배너</본명>
//   </members>
// </root>

// JSON.parse
// 서버에서 받은 데이터를 객체(object, array)로 변환
const json = '{"result":true, "count":42}';
console.log(json[0])

const obj = JSON.parse(json);
console.log(obj); // 문자열에서 객체로 변환
console.log(obj['result']);


const json2 = '[10, 20, 30]';
console.log(json2[0])

const obj2 = JSON.parse(json2);
console.log(obj2); // 문자열에서 객체로 변환
console.log(obj2[0]);

// JSON.stringify
// 객체(object, array)를 문자열로 변환
// 내가 작성한 데이터를 서버로 전송할 때 사용

const obj3 = { result: true, count: 42 };
const obj4 = { result: [10, 20, 30], count: 42 };
const json3 = JSON.stringify(obj3);
const json4 = String(obj4);
const json4_ = JSON.stringify(obj4);

console.log(json3);
console.log(json4);
console.log(json4_);

console.log(json3[0]); // 객체에서 문자열로 변환
console.log(json3[1]);
```
## 8. DOM
### 8.1 DOM API
* DOM은 HTML 문서의 내용을 트리 형태로 구조화하여 웹페이지와 프로그래밍 언어를 연결시켜주는 역할
* DOM은 웹 페이지를 조작하고 수정할 수 있게 해주는 중요한 개념
* 각각의 요소와 속성, 콘텐츠를 표현하는 단위를 '노드(node)' 라고 함
<img src="/posts/img/domtreecode.png" width="450px" height="300px" title="돔 트리 코드" alt="domtreecode.png"></img><br/>
<img src="/posts/img/domtree.png" width="450px" height="300px" title="돔 트리" alt="domtree.png"></img><br/>
### 8.1.1 DOM 트리에 접근하기
    1. getElementById : 해당 ID를 가진 요소에 접근
    2. getElementsByTagName : 해당하는 태그 이름을 가진 모든 요소에 접근
    3. getElementsByClassName : 해당하는 클래스를 가진 모든 요소에 접근
    4. querySelector : CSS 선택자를 사용해 단일 요소에 접근
    5. querySelectorAll : CSS 선택자를 사용하여 여러 요소에 접근
```
<body>
    <h1 id="logo" class="title">hello world</h1>
    <section>
        <h2 id="section-title">HTML 1</h2>
        <p id="contents">HTML is HyperText Markup Language. 1</p>
    </section>
    <section>
        <h2 id="section-title">HTML 2</h2>
        <p id="contents">HTML is HyperText Markup Language. 2</p>
    </section>
    <p class="hello">hello world</p>
<script>
const logo = document.getElementById('logo'); // 
const sectionTitle = document.querySelector('#section-title'); // 
const sectionTitleAll = document.querySelectorAll('#section-title');
const hello = document.querySelector('.hello');

console.log(logo);
console.log(sectionTitle);
console.log(sectionTitleAll);
console.log(hello);
</script>
</body>
```
### 8.2 DOM 제어하기
```
<button class="hello">HELLO!</button>

const myBtn = document.querySelector('button');

// 1. 이벤트 추가
// myBtn.addEventListener('click', () => {
//     console.log('hello world');
// });

// 2. 클래스 제어
// myBtn.classList.add('blue');
myBtn.addEventListener('click', function () {
    // myBtn.classList.add("blue"); // 클래스를 추가합니다.
    // myBtn.classList.remove("blue"); // 클래스를 제거합니다.
    myBtn.classList.toggle('blue'); // 클래스를 토글합니다.
    console.log(myBtn.classList.contains('blue')); // 클래스가 있는지 확인합니다.
});

// 3. 요소 제어
// 이 데이터는 통신을 통해 받아온 데이터 입니다.
/*
document.createElement(target) : target 요소를 생성
document.createTextNode(target) : target 텍스트를 생성
element.appendChild(target) : target 요소를 element의 자식으로 위치
element.removeChild(target) : element의 target 자식 요소를 제거
element.append(target) : target 요소를 element의 자식으로 위치. appendChild 와 다른점은 노드 뿐만 아니라 여러개의 노드를 한번에, 그리고 텍스트도 자식 노드로 포함시킬 수 있다는것
target.remove() : target 요소를 제거합니다.
*/
1.3.1 요소 생성 및 추가
// document.createElement() 메서드를 사용하여 새로운 요소를 생성
// element.appendChild() 메서드를 사용하여 생성한 요소를 추가
// element.removeChild() 메서드를 사용하여 요소를 제거
const data = {
    name: 'hello',
    content: 'world',
    price: 3000
};

const section = document.createElement('section');
const name = document.createElement('h2');
const content = document.createElement('p');
const price = document.createElement('p');
const img = document.createElement('img');

// img.setAttribute('src', 'https://via.placeholder.com/300');
img.src = 'https://via.placeholder.com/300';
name.textContent = data.name;
content.textContent = data.content;
price.textContent = data.price;
price.style.color = 'red';
// font-size -> fontSize
price.style.fontSize = '20px';

section.appendChild(img);
section.appendChild(name);
section.appendChild(content);
section.appendChild(price);

// document.body.appendChild(section);
document.body.append(section); // appendChild 와 다른점은 노드 뿐만 아니라 여러개의 노드를 한번에, 그리고 텍스트도 자식 노드로 포함시킬 수 있다는것 입니다.
```
추가로
요소의 스타일을 제어하는 style 객체
요소의 속성을 제어하는 setAttribute() 메서드
요소의 속성을 제거하는 removeAttribute() 메서드 가 있음

### 8.3 DOM의 이벤트 흐름
* 브라우저가 이벤트 대상을 찾아갈 때는 가장 상위의 window 객체부터 document, body 순으로 DOM 트리를 따라 내려감 이를 캡처링 단계라고 합
* 이때 이벤트 대상을 찾아가는 과정에서 브라우저는 중간에 만나는 모든 캡처링 이벤트 리스너를 실행시킴. 그리고 이벤트 대상을 찾고 캡처링이 끝나면 이제 다시 DOM 트리를 따라 올라가며 만나는 모든 버블링 이벤트 리스너를 실행함. 이를 이벤트 버블링 단계라고 함.
* 그리고 이러한 과정에서 이벤트 리스너가 차례로 실행되는것을 이벤트 전파라고 함

## 10. 비동기 프로그래밍
### 10.1 비동기 프로그래밍과 Promise
