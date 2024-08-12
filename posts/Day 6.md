JAVASCRIPT
======================
## 1. JavaScript의 기초
### 1.1 콘솔 기능
```
console.log(); // 콘솔창에 로그 메시지를 보여줍니다.
console.error(); // 콘솔창에 에러 메시지를 보여줍니다.
console.warn(); // 콘솔창에 경고 메시지를 보여줍니다.
console.info(); // 콘솔창에 정보 메시지를 보여줍니다.
console.table(); // 콘솔창에 데이터를 테이블 형태로 제공합니다.
```

### 1.2 브라우저 객체 모델
```
window.alert('경고 메시지'); // 브라우저에 메시지 다이얼로그를 띄웁니다.
window.prompt('이름을 입력하세요'); // 브라우저에 사용자 입력 창을 띄웁니다.
window.confirm('확인하시겠습니까?'); // true 혹은 false 값을 반환하는 다이얼로그를 띄웁니다.
window.console.log('hello world!'); // 콘솔창에 로그 메시지를 보여줍니다.
```

### 1.3 주석
* `//` 단일 행 주석
* `/*` `*/` 다중 행 주석

### 1.4 변수 생성
* `var` 함수 스코프, 함수 외부에서 선언되면 전역 변수로 동작함. 재선언이 가능해 복잡을 야기하므로 사용을 권장하지 않음
* `let` 블록 스코프
* `const` 블록 스코프, 재할당 불가능. 상수

### 1.5 변수 이름의 규칙
```
  1. 변수 이름은 알파벳(대문자와 소문자), 숫자, 언더스코어`_`, 달러`$`로 구성됩니다. `$`, `_` 를 제외한 공백, 특수문자, 구두점(글의 여러 가지 경계를 구분하기 위해 사용되는 반점(,), 온점(.), 물음표(?), 띄어쓰기 등)을 사용할 수 없습니다.
  2. 변수 이름은 숫자로 시작할 수 없습니다. 
  3. 키워드(예: if, else, while 등)는 변수 이름으로 사용할 수 없습니다.
  4. 예약어가 쓰일 수 없습니다.
  5. 변수 이름은 대소문자를 구분합니다
  6. 일반 변수는 첫 문자를 소문자로 쓰는 것이 보통입니다.
  7. 사용하지 않는 변수는 언더스코어(_)로 명명합니다. test → _test
  8. 클래스는 첫 문자를 대문자로 사용합니다. class Test():
  9. 변수 이름은 카멜 표기법을 주로 사용합니다. (선호하는 변수명은 언어마다 다릅니다.)
```
스네이크 표기법
```
daily_user_count = 100;
```
카멜 표기법
```
dailyUserCount = 100;
```
파스칼 표기법
```
DailyUserCount = 100;
```
### 1.6 변수의 타입
* typeof 연산자는 변수의 타입을 문자열로 반환합니다.
```
let age = 10;
console.log(typeof age); // "number"

let name = 'Jun';
console.log(typeof name); // "string"
```
typeof age : number 반환 
typeof name : string 반환
### 1.7 변수 값 변경
```
let x = 10;
console.log(x);

x = 20;
console.log(x);
```
### 1.8 중괄호의 사용법
```
if (true) {
   let value = 'hello';
   console.log(value);
}
```

## 2. 원시타입과 문자열 자료형
### 2.1 타입 확인하기
```
//typeof를 활용한 타입 확인
let num = 1234;
let str = 'jeju';
console.log(typeof num); // 'number'
console.log(typeof str); // 'string'

js에서는 배열이 객체라서 Object.prototype.toString.call 를 사용해 확인
let arr = [1, 2, 3];
console.log(typeof arr); // 'object'
console.log(Object.prototype.toString.call(arr)); // '[object Array]'
```

### 2.2 타입의 종류
### 2.2.1 원시타입
* 가리키고 있는 값이 변경 불가능함
* 숫자 (Number): 숫자를 나타냅니다.
* 문자열 (String): 텍스트를 나타냅니다.
* 불리언 (Boolean): 참(true) 또는 거짓(false)을 나타냅니다.
* 심볼 (Symbol): 고유한 식별자를 나타냅니다.
* undefined: 변수가 값을 갖고 있지 않음을 나타냅니다.
* null: 값이 없음을 나타냅니다.

### 2.2.2 참조타입
* 객체 (Object): 키-값 쌍을 저장합니다.
* 배열 (Array): 순서가 있는 리스트를 저장합니다.
* 함수 (Function): 실행 가능한 코드를 저장합니다.

### 2.3 문자열
### 2.3.1 문자열의 특징
* 문자열은 순서가 있습니다. 순서는 0부터 시작하며 띄어쓰기도 문자로 취급합니다.
* 이 순서를 index라고 부르며 아래와 같이 각괄호([ ])를 사용해 특정 순서에 위치한 글자를 가져올 수 있습니다
``` 
let text = 'hello world';
console.log(text[0]);
console.log(text[6]);
h w
```
* 문자열은 length 라는 속성이 있습니다. length 속성을 통해 문자열의 길이를 구할 수 있습니다.
```
let myPassword = 'qwer123!@#';
console.log(myPassword.length);
10
```
* 한번 만들어진 문자열은 변하지 않습니다
```
let 불변성 = 'immutable';
// 불변성[0] = 'l';
// console.log(불변성);

console.log(불변성.toUpperCase());
console.log(불변성);
"IMMUTABLE"
"immutable"
```
* 문자열은 +연산자로 연결될 수 있습니다. 문자열은 연결된 순서만 동일하다면 같은 문자열로 판단합니다. ==는 같은지를 비교하는 연산자
```
let one = 'hello';
let two = ' world';

console.log(one + two);
console.log('hello world' == one + two);
"hello world"
true
```

### 2.3.2 문자열 메소드
  1. indexOf()
>문자열 안에 존재하는 특정한 문자를 검색하여 문자의 인덱스를 반환합니다. 검색할 문자와 검색을 시작할 인덱스 번호 두 가지를 인자로 전달 할 수 있습니다. 문자열 안에 검색하고자하는 문자가 존재하지 않으면 -1을 반환합니다.

  2. replace()

  3. slice()

  4. split()

  5. toLowerCase(), toUpperCase()

  6. trim()
