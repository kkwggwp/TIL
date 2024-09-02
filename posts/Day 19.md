# Daily Quiz 9/2

## 1. 아래 2개의 변수 number1, number2의 사칙 연산 결과(result1 ~ result4)를 정수로 출력하세요. (사칙연산: +, -, *, /) 주석처리 된 곳에 코드를 채우면 됩니다
```
public class Question {
    public static void main(String args[]) {
        int number1 = 10;
        double number2 = 2.0;

        int result1 = (int)(number1 + number2);
        int result2 = (int)(number1 - number2);
        int result3 = (int)(number1 * number2);
        int result4 = (int)(number1 / number2);

        System.out.println(result1);
        System.out.println(result2);
        System.out.println(result3);
        System.out.println(result4);
    }
}
```

## 2. 아래 코드의 출력값은 무엇일까요? 코드를 돌려보기 전에 예측해보세요.
### 2.1
```
public class Question {
    public static void main(String args[]) {
        // 다음 문장들의 출력 결과를 확인해보세요.
        System.out.println("10" + "04");
        System.out.println("" + false);
        System.out.println('a' + 100);
    }
}
```
> 17

### 2.2
```
public class Question {
    public static void main(String args[]) {
        // 아래 코드의 출력값은 무엇일까요?
        int number = 10;
        
        int result1 = number + 1;
        int result2 = number++;
        int result3 = number;
        int result4 = --number;
        
        System.out.println(result1);
        System.out.println(result2);
        System.out.println(result3);
        System.out.println(result4);
    }
}
```

> 11, 10, 11, 10

### 2.3
```
public class Question {
    public static void main(String args[]) {
        // 아래 코드의 출력값은 무엇일까요?
        int num1 = 5;
        int num2 = 7;

        System.out.println((num1 > 5) && (num2 > 5));
        System.out.println((num1 > 5) || (num2 > 5));
        System.out.println(!((num1 > 5) && (num2 > 5)));
    }
}
```

> false, true, true

## 3. 다음의 내용을 연산식(조건식)으로 표현해보세요.
*i는 2의 배수 또는 3의 배수이다.
```
(i % 2 == 0) || (i % 3 == 0)
```

## 4. 아래 코드의 실행 결과가 true가 되도록 수정해보세요.
문제
```
public class Question {
    public static void main(String args[]) {
        // 아래 코드의 실행 결과가 true가 되도록 수정해보세요.
        String str1 = new String("Hello world!");
        String str2 = new String("Hello world!");
        
        System.out.println(str1 == str2);
    }
}
```
수정
```
public class Question {
    public static void main(String args[]) {
        // 아래 코드의 실행 결과가 true가 되도록 수정해보세요.
        String str1 = "Hello world!";
        String str2 = "Hello world!";
        
        System.out.println(str1 == str2);
    }
}
```

## 5. 프로그래머스 문제
### 5.1 공배수
* 정수 number와 n, m이 주어집니다. number가 n의 배수이면서 m의 배수이면 1을 아니라면 0을 return하도록 solution 함수를 완성해주세요.
```
public class Solution {
    public int solution(int number, int n, int m) {
        return number % n == 0 && number % m == 0 ? 1 : 0;
    }
}
```

### 5.2 n의 배수
* 정수 num과 n이 매개 변수로 주어질 때, num이 n의 배수이면 1을 return n의 배수가 아니라면 0을 return하도록 solution 함수를 완성해주세요.
```
public class Solution {
    public int solution(int num, int n) {
        return num % n == 0 ? 1 : 0;
    }
}
```

### 5.3 flag에 따라 값 반환하기
* 두 정수 a, b와 boolean 변수 flag가 매개변수로 주어질 때, flag가 true면 a + b를 false면 a - b를 return 하는 solution 함수를 작성해 주세요.
```
class Solution {
    public int solution(int a, int b, boolean flag) {
        return flag ? a + b : a - b;
    }
}
```
