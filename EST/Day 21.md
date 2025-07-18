# Daily Quiz 9/4

## 1. for문을 이용해서 a배열의 값을 b배열로 복사해보세요.
```
public class Question {
    public static void main(String args[]) {
        // for문을 이용해서 a배열의 값을 b배열로 복사해보세요.
        int[][] a = {{1, 2, 3}, {4, 5, 6}};
        int[][] b = new int[3][3];
        
        // for문 작성하는 부분
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                b[i][j] = a[i][j];
            }
        }
        // …
        
        // a배열과 b배열 출력
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                System.out.println("a[" + i + "][" + j + "]: " + a[i][j]);
                System.out.println("b[" + i + "][" + j + "]: " + b[i][j]);
            }
        }
    }
}
```

## 2. for문을 이용하여 배열에 있는 숫자들의 최대값과 평균을 구하세요.

```
public class Question {
    public static void main(String args[]) {
        // for문을 이용하여 배열에 있는 숫자들의 최대값과 평균을 구하세요.
        int[] array = {12, 4, 7, 20, 1};
        
        // 코드 작성하는 부분
        int max = array[0];
        int sum = 0;
        for (int i = 0; i < array.length; i++) {
            if (array[i] > max) {
                max = array[i];
            }
            sum += array[i];
        }
        float avg = sum / array.length;
        // ...
        
        // 결과 출력 (최대값: max, 평균: avg)
        System.out.println(max);
        System.out.println(avg);
    }
}
```
> 20, 8.0

## 3. 0부터 20까지 짝수만 출력하는 코드를 작성해보세요.
```
public class Question {
    public static void main(String args[]) {
        // 0부터 20까지 짝수만 출력하는 코드를 작성해보세요.
        for (int i = 0; i <= 20; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            };
        }
    }
}
```
또는
```
for (int i = 0; i <= 20; i += 2) {
            System.out.println(i);
        }
```

## 4. 프로그래머스 문제
### 4.1. 정수 n이 주어질 때, n이하의 짝수를 모두 더한 값을 return 하도록 solution 함수를 작성해주세요.
```
class Solution {
    public int solution(int n) {
        int answer = 0;
        for (int i = 0; i <= n; i += 2) {
            answer += i;
        }
        return answer;
    }
}
```

### 4.2 정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.
```
class Solution {
    public double solution(int[] numbers) {
        float sum = 0, answer = 0;
        for (int i : numbers) {
            sum += i;
        }
        answer = sum / numbers.length;
        return answer;
    }
}
```
