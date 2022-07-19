# 평균 구하기
***

## 문제 설명
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

## 제한 조건
* arr은 길이 1 이상, 100 이하인 배열입니다.
* arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

***
내가 푼 풀이
```java
class Solution {
    public double solution(int[] arr) {
        double answer = 0;
        int su = 0;

        for(int i=0; i<arr.length; i++){
            su += arr[i];
        }

        answer = (double)su / arr.length;

        return answer;
    }
}
```

다른 사람이 푼 풀이
```java
import java.util.*;
import java.lang.*;

class Solution {
    public double solution(int[] arr) {

        return Arrays.stream(arr).average().getAsDouble();
    }
}
```
* Stream 의 average().getAsDouble()를 통해 Double로 평균을 구한다.
