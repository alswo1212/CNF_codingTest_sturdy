+ 기존 풀이
```java
class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        int len = citations.length;
        int[] cnts = new int[len];

        for(int citation : citations){
            int temp = citation > len ? len : citation;
            if(temp == 0)
                continue;
            cnts[temp - 1]++;
        }

        for(int i = len - 2; i >= 0; i--){
            cnts[i] += cnts[i+1];
        }

        for(int i = 0; i < len; i++){
            if(i+1 > cnts[i]){
                break;
            }
            answer++;
        }

        return answer;
    }
}
```
![image](https://github.com/alswo1212/CNF_codingTest_sturdy/assets/92290312/22ed35f2-e5ca-467b-896a-d183ddfac4e8)
