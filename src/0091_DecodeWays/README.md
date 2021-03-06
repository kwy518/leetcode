1. We should think the easier version:
    - Is similar to the ladder problem.
    - f(n) = f(n-1) + f(n-2)
  
2. f(n) = f(n-1) + f(n-2), but there are some conditions to be considered.
    - Plus f(n - 1) only if **s(n-1) is not 0.**
    Since 0 do not match to any letter, for instance, "10" should only count as 1 way to decode.
    ```java
            if(s.charAt(i-1) != '0'){
               dp[i] += dp[i-1];
            }
    ```
    - Plus f(n - 2) only if the number composed of s(n-2) and s(n-1) is located from 10 to 26, which match with one more letter.
    ```java
            int n = (s.charAt(i-2) - '0') * 10 + (s.charAt(i-1) - '0');
            if(n <= 26 && n >= 10){
                dp[i] += dp[i-2];
            }
    ```
