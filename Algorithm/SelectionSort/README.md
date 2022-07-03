# Selection Sort 선택정렬
해당 순서에 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택하는 알고리즘

***
## 장점
* 알고리즘이 단순하다.
* 정렬하고자 하는 배열안에서 교환하는 방식이여서 다른 메모리 공간을 필요로 하지 않는다.
## 단점
* 시간이 오래걸려 비효율적이다.
***
## 방법
숫자를 입력받아서, 그 숫자만큼의 선택 정렬을 하는 방식
1. 주어진 배열 중에 최소값을 찾는다.
2. 그 값을 맨 앞에 위치한 값과 교체한다.
3. 맨 처음 위치를 뺀 나머지 배열을 같은 방법으로 교체한다.

```java
public class Bubble{
    public static void main(String[] args){
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        
        System.out.print("숫자의 개수를 입력하세요: ");
        int numSu = Integer.parseInt(br.readLine());
        int num[] = new int[numSu];

        for(int i=0; i<num.length; i++){
            System.out.println("숫자" + (i+1) + ": ");
            num[i] = Integer.parseInt(br.readLine());
            }

        for (int a = 0; a < num.length-1; a++){
            int min = a; //min = 최솟값을 저장
            for(int b = a+1; b < num.length; b++){
                if(num[b]<num[min]){
                    min=b;}
                }
            int temp = num[min]; //temp 이란 변수에 일단 임시 저장해 놓는 것.
            num[min] = num[a];
            num[a] = temp;
        }
        
        System.out.println("결과 출력: ");
        for (int z=0; z<num.length; z++){
            System.out.print(num[z] + " ");
        }
        System.out.println();
    }
}
```

## 결과
![img.png](img.png)