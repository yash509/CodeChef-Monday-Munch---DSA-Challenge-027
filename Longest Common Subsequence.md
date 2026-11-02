### Problem
Given two strings S and R, find the length of their longest common subsequence.

**Input**
- First line: T
- Each test case: two space-separated strings S and R

**Output**
- For each test case print the length of the LCS.

**Constraints**
- 1 ≤ T ≤ 50
- 1 ≤ |S|, |R| ≤ 100

**Explanation**
- Classic DP solution.
- dp[i][j] = length of LCS of the first i characters of S and first j characters of R.

- If S[i-1] == R[j-1] → dp[i][j] = dp[i-1][j-1] + 1
- Else → dp[i][j] = max(dp[i-1][j], dp[i][j-1])

**Dry Run (Sample 1):**
- S = "abcde", R = "ace"
- LCS = "ace" → length 3

### Solution (C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    int T;
    cin >> T;
    
    while (T--) {
        string S, R;
        cin >> S >> R;
        
        int n = S.length();
        int m = R.length();
        
        int dp[105][105];
        memset(dp, 0, sizeof(dp));
        
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (S[i - 1] == R[j - 1]) {
                    dp[i][j] = dp[i - 1][j - 1] + 1;
                } else {
                    dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        
        cout << dp[n][m] << "\n";
    }
    
    return 0;
}
