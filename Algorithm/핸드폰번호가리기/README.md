# 핸드폰 번호 가리기
***

## 문제 설명
전화번호가 문자열 phone_number로 주어졌을 때,  
전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 *으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

## 제한 조건
* phone_number는 길이 4 이상, 20이하인 문자열입니다.

***
내가 푼 풀이
```java
class Solution {
    public String solution(String phone_number) {
        String answer = "";
        
        int len = phone_number.length();
        for(int i=0; i<len-4; i++){
            answer += "*";
        }
        answer += phone_number.substring(len-4);
        return answer;
    }
}
```

다른 사람이 푼 풀이 (정규식)
```java
class Solution {
  public String solution(String phone_number) {
    return phone_number.replaceAll(".(?=.{4})", "*");
  }
}
