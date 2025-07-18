JAVASCRIPT
======================
## 3. 함수
### 3.2 함수의 활용
### 3.2.1 추상화
```
// 추상화
// 자동차 운전을 한다

// 핸들
// 엑셀
// 브레이크
// 기어

// 핸들이 실제로 어떻게 동작하는지 알 필요가 있나요?
// 엑셀하고 엔진이 실제로 어떻게 동작하는지 알 필요가 있나요?
// 브레이크가 실제로 어떻게 동작하는지 알 필요가 있나요?
// 기어가 실제로 어떻게 동작하는지 알 필요가 있나요?

// 추상화를 이해하는 것이 왜 중요하죠?
// 코딩을 처음 배우게 되면 추상화를 안합니다. 함수로 만들거나 클래스로 만드는 작업을 하지 않아요. 그냥 쭉 써요.
// 추상화를 하게 되면 코드의 재사용성을 높일 수 있고, 유지보수성을 높일 수 있습니다.

// function greet(name) {
//     console.log(`안녕하세요, ${name}님!`);
//     return undefined;
// }

// 위 코드와 동일합니다.
function greet(name) {
    console.log(`안녕하세요, ${name}님!`);
}

console.log(greet("licat"));
console.log(greet("mura"));
console.log(greet("binky"));
```
### 3.2.2 콜백 함수
```
// 일급 함수란?
// 함수를 값으로 다룰 수 있다.
let a = console.log;
let b = alert;
let c = confirm;
let d = parseInt;

a("Hello, World!");

// 콜백 함수
// 나중에 널 불러줄께!
// 함수를 값으로 다루는 기술 중 하나
// 함수를 다른 함수의 인자(아규먼트)로 넘길 수 있다.
// (함수를 리턴할 수도 있다.)

function licat(f1, f2) {
    f1(f2("10") + f2("20"));
    return f1;
}

licat(a, d)
```
### 3.2.3 함수를 선언하는 여러가지 방법
```
// 함수 선언문
function sum1(x, y) {
    return x + y;
}

// 함수 표현식
let sum2 = function (x, y) {
    return x + y;
};

// 화살표 함수
let sum3 = (x, y) => x + y;


// 화살표 함수 다른 형태 - 2
let sum4 = (x, y) => {
    let z = x + y;
    return z;
};

// 화살표 함수 다른 형태 - 3
let sum5 = x => {
    let z = x * 2;
    return z;
};

console.log(sum1(10, 20));
console.log(sum2(10, 20));
console.log(sum3(10, 20));
```

## 4. 객체 타입에 관하여
### 4.1 객체타입과 배열
```
// 객체 타입: 여러 개의 값을 하나의 단위로 구성한 복합 자료형
// 원시 타입과 달리 값 변경이 가능

// 객체
const obj = {
    name: '홍길동',
    age: 16,
    address: '서울',
}

// 배열
const arr = [1, 2, 3, 4, 5];
// 다차원 배열
const arr2 = [
    [1, '홍길동', 70, 80, 90],
    [2, '홍길순', 60, 70, 80],
    [3, '홍길만', 50, 60, 70],
]
console.table(arr2);
```
### 4.1.1 배열의 메소드
```
// 1. push 배열의 끝에 요소를 추가하고 길이를 반환, pop 메소드는 배열의 마지막 요소를 꺼내어 반환
const arr = [1, 2, 3];
arr.push(4);
console.log(arr); // [1, 2, 3, 4]

arr.pop();
console.log(arr); // [1, 2, 3]

const arr2 = [1, 2, 3];
const last = arr2.pop();
console.log(last); // 3

// 2. shift 배열에서 첫 번째 요소를 꺼내어 반환, unshift 배열의 첫 번째 요소로 새로운 요소를 추가
const arr3 = [10, 20, 30];
arr3.shift();
console.log(arr3); // [20, 30]

arr3.unshift(40, 50);
console.log(arr3); // [40, 50, 20, 30]

arr3.unshift(100);
console.log(arr3); // [100, 40, 50, 20, 30]

// push
// pop
// unshift
// shift

// 스택(정보처리기사 문제에서 많이 나옵니다.)
// 스택은 과자 상자라고 생각을 하겠습니다.
// 나중에 들어간 과자가 먼저 나오게 됩니다.
// push, pop으로 stack 구현하기 - 1
const stack = [];
stack.push(1);
stack.push(2);
stack.push(3);
console.log(stack); // [1, 2, 3]
stack.pop();
// stack.shift(); // 이렇게 하면 스택이 깨진겁니다.

// shift, unshift로 stack 구현하기 - 2
const stack2 = [];
stack2.unshift(1);
stack2.unshift(2);
stack2.unshift(3);
console.log(stack2); // [3, 2, 1]


// 큐
// 큐는 원통 놀이기구라고 생각을 하겠습니다.
// 먼저 들어간 사람이 먼저 나오게 됩니다.
// push, shift로 queue 구현하기 - 1
const queue = [];
queue.push(1);
queue.push(2);
queue.push(3);
console.log(queue); // [1, 2, 3]
queue.shift();

// unshift, pop으로 queue 구현하기 - 2
const queue2 = [];
queue2.unshift(1);
queue2.unshift(2);
queue2.unshift(3);
console.log(queue2); // [3, 2, 1]
queue2.pop();

// 3. slice 배열에서 요소들을 추출하여 새로운 배열로 반환
// string에서 했었던 것과 같은 방식으로 사용할 수 있습니다.
const arr = [10, 20, 30, 40, 50];
console.log(arr.slice(2)); // [30, 40, 50]
console.log(arr.slice(2, 4)); // [30, 40]

// 4. sort
// 배열을 정렬합니다. 기본적으로는 오름차순으로 정렬합니다.
const arr2 = [20, 10, 50, 40, 30];
arr2.sort();

// 5. forEach 배열의 각 요소에 대해 주어진 함수를 실행
const a = [10, 20, 30, 40, 50];
a.forEach((value, index, object) => {
    console.log(value, index, object)
})

// 6. map 배열의 각 요소에 대해 주어진 함수를 실행하고, 그 결과를 새로운 배열로 반환
// forEach는 반복만 합니다.
// map 새로운 배열을 생성합니다.
const d = [1, 2, 3, 4, 5];
const e = d.map(v => v * v);

// 7. includes 배열에 특정 요소가 포함되어 있는지를 확인하여, 포함되어 있으면 true, 그렇지 않으면 false를 반환
const arr1 = ['hello', 'world', 'hojun'];
console.log(arr1.includes('world')); // true - 'world'가 배열에 포함됨

const arr2 = ['hello', 'world', 'hojun'];
console.log(arr2.includes('leehojun')); // false - 'leehojun'이 배열에 포함되지 않음

const arr3 = ['hello', 'world', 'hojun'];
console.log(arr3.includes('jun')); // false - 'jun'이 배열에 포함되지 않음

const arr4 = [10, 20, 30, 40];
console.log(arr4.includes(10));

// 8. join 배열의 모든 요소를 연결하여 하나의 문자열로 만듬
const arr5 = ['hello', 'world', 'hojun'];
arr5.join(' ');
arr5.join('-');

const phone = '010-5044-2903'.split('-')
console.log(phone.join(''));

```
### 4.2 객체
```
// 객체
const d = {
    name: 'hojun',
    age: 27,
    height: 180
};

console.log(d);
console.log(d['name']); // 이 방식을 권고합니다!
console.log(d.name);

delete d.age; // 사용을 많이 하지 않습니다.
console.log(d);

// 4. in 연산자 객체 속성 확인
// in은 key값만 기준으로 합니다.
'name' in d; // true
// 그런데 왜 아래 예제는 false가 나올까요?
10 in [10, 20, 30, 40]; // false
// 이 배열 안에 있는 [10]은 key값이 아니라 value라서 그렇습니다.
0 in [10, 20, 30, 40]; // true

// 유사배열객체
const arr = {
    0: 10,
    1: 20,
    2: 30,
    3: 40,
    length: 4
}

console.log(arr);
console.log(arr[0]);

// 5. 객체의 중첩

const company = {
    name: 'Continental',
    location: {
        city: 'New York',
        country: 'USA'
    },
    employees: {
        manager: 'Winston',
        concierge: 'Charon'
    }
};

console.log(company.location.city); // New York
console.log(company.employees.manager); // Winston
console.log(company['employees']['manager']); // Winston

// 객체의 메소드
const obj = {
    name: 'hojun',
    age: 27,
    height: 180
};
```
## 5. 코드 제어
### 5.1 조건문
```
// 1. if문
let 초록불 = false;

if (초록불) {
    console.log('횡단보도를 건넙니다.');
} else {
    console.log('기다립니다.');
}

if (true) {
    console.log('실행합니다');
}

if (false) {
    console.log('실행합니다1');
    if (true) {
        console.log('실행합니다2');
    }
}

if (3 < 10) {
    console.log('실행합니다3');
}

const value1 = 'hello'; // true 판단
const value2 = ''; // false 판단
const value3 = null; // false 판단
const value4 = []; // 주의!! 빈 배열도 true 판단

if (value4){
    console.log('value1은 Truthy한 값입니다.');
}

// 한 줄의 경우 중괄호 생략 가능합니다.
if (true) console.log('중괄호를 생략했습니다.');

// if, else if, else
let score = 91;
let grade;

if (score > 90) {
    grade = 'A';
} else if (score > 80) {
    grade = 'B';
} else if (score > 70) {
    grade = 'C';
} else if (score > 60) {
    grade = 'D';
} else {
    grade = 'F';
}

console.log(`당신의 학점은 ${grade}입니다.`);


// 만약 위 구문이 if문으로만 되어 있다면 무슨 문제가 있는지 확인해보세요.
let score1 = 91;
let grade1;

if (score1 > 90) {
    grade = 'A';
}
if (score1 > 80) {
    grade = 'B';
}
if (score1 > 70) {
    grade = 'C';
}
if (score1 > 60) {
    grade = 'D';
}
console.log(`당신의 학점은 ${grade}입니다.`);

// 2. switch문, break
// break가 없으면 조건이 참일시 이후 모든 코드 실행
let fruit = 'apple';
switch (fruit) {
    case 'banana':
        console.log('바나나입니다.');
        break;
    case 'apple':
        console.log('사과입니다.');
        break;
    case 'mango':
        console.log('망고입니다.');
        break;
    default:
        console.log('일치하는 과일이 없습니다.');
}

const attackType = '빔공격';

switch (attackType) {
    case '빔공격':
    case '할퀴기공격':
        console.log('10에 데미지를 입혔습니다.')
        break;
    case '방어막공격':
        console.log('5에 데미지를 입혔습니다.')
        break;
    }

switch (2) {
    case 1:
        console.log('월요일입니다.');
        break;
    case 2:
        console.log('화요일입니다.');
        break;
    case 3:
        console.log('수요일입니다.');
        break;
    case 4:
        console.log('목요일입니다.');
        break;
    case 5:
        console.log('금요일입니다.');
        break;
    default:
        console.log('주말입니다.');
        break;
}

switch (2) {
    case 1:
        console.log('월요일입니다.');
    case 2:
        console.log('화요일입니다.');
    case 3:
        console.log('수요일입니다.');
    case 4:
        console.log('목요일입니다.');
    case 5:
        console.log('금요일입니다.');
    default:
        console.log('주말입니다.');
}
```
### 5.2 반복문
```
// 1. for문
let x = 10;
x = x + 10; // x가 반복되니 줄이고 싶다!
x += 10; // x = x + 10; 과 같은 의미입니다.
console.log(x);

for (let i = 0; i < 10; i += 3) {
    console.log(i);
}

/////////////////////

for (let i = 2; i <= 9; i++) {
    for (let j = 1; j <= 9; j++) {
        console.log(`${i} x ${j} = ${i * j}`);
    }
}
-------------------------------------------
// 2. while문
let x = 0;

while (x < 10) {
    console.log(x);
    x++;
}

// 무한 루프
// 메모리를 어마어마하게 많이 잡아먹습니다. 그래서 무한루프의 경우 서버가 다운되거나, 브라우저가 다운되는 경우가 있습니다.

let num = 0;
while (num <= 10) {
    console.log(num);
    if (num === 5) {
        break; // num이 5일 때 반복문을 종료합니다.
    }
    num++;
}

let num2 = 0;
let num3 = 0;
while (num2 <= 10) {
    while (num3 <= 10) {
        console.log(num2, num3);
        if (num3 === 5) {
            break;
        }
        num3++;
    }
    // if (num3 === 5) {
    //         break;
    // }
    num2++;
}

for (let i = 0; i < 20; i++) {
    if (i < 13) {
        continue; // i가 13 미만이면 아래 코드를 건너뜁니다.
    }
    console.log(i + '살은 청소년입니다.');
}
```
### 5.3 전개 구문과 Destructuring
```
// 1. 전개구문
// 배열이나 객체같은 데이터 구조를 확장하기 위해 사용
Math.max(1, 2, 3, 4, 5); // 5
Math.max([1, 2, 3, 4, 5]); // NaN

const numbers = [1, 2, 3, 4, 5];
Math.max(numbers); // NaN
Math.max(...numbers); // 5

const a = [1, 2, 3];
const b = [4, 5, 6];
const c = [...a, ...b]; // [1, 2, 3, 4, 5, 6]
const d = [a, ...b]; // [[1, 2, 3], 4, 5, 6]


const 과일들 = ['사과', '파인애플', '수박'];
const 과일들2 = 과일들

과일들2[0] = '포도';
console.log(과일들); // ['포도', '파인애플', '수박']

const 과일들3 = [...과일들];
과일들3[0] = '바나나';
console.log(과일들); // ['포도', '파인애플', '수박']

const one = ['사과', '파인애플', '수박']
const two = ['사과', '파인애플', '수박']
console.log(one === two); // false


const 위니브1 = { 개리: 1, 빙키: 2 };
const 위니브2 = { 라이캣: 3 };
const 위니브3 = { ...위니브1, ...위니브2 };

console.log(위니브3);
----------------------------------------
// 2. 디스트럭쳐링
// 데이터 구조를 분해하여 변수에 할당
const [a, b, c] = [1, 2, 3];

console.log(a); // 1
console.log(b); // 2
console.log(c); // 3

// let food1, food2, food3;

// const categories = { food1: '과일', food2: '채소', food3: '육류' };

// food1 = categories.food1;
// food2 = categories.food2;
// food3 = categories.food3;

// console.log(food1);
// console.log(food2);
// console.log(food3);

const { food1, food2, food3 } = { food1: '과일', food2: '채소', food3: '육류' };

console.log(food1);
console.log(food2);
console.log(food3);
```
## 6. 조금 더 깊이 들여다보기
### 6.1 this
```
// this는 글로벌 기업에서도 이 코드의 사용을 주의해서 사용하거나 지양하는 경향이 있습니다.
// this는 상황에 따라 다르게 동작할 수 있기 때문에 외워야 하는 예외 케이스가 너무 많습니다.
// this는 '나 자신 + @'이라고 생각을 해주시면, 초급자 분들에게는 충분하다 생각합니다.

console.log(this); // window
window.alert('hello');
this.alert('hello');

function f() {
    console.log(this); // window
}
f();

const obj = {
    name: 'licat',
    f: function () {
        console.log(this);
    },
};

obj.f(); // obj

function Person(name) {
    this.name = name;
    console.log(this);
    // return this
}

const person1 = new Person('licat'); 
// Person { name: "licat" }
const person2 = new Person('mura');
// Person { name: "mura" }
```
