### Problem
Given two strings S and R, find the length of their longest common subsequence.

### Problem in Simple Words

You are given two strings S and R.

A subsequence is formed by deleting some characters without changing the order of remaining characters.

We need the length of the longest subsequence that appears in both strings.Example:

S = "abcde", R = "ace" → common subsequence "ace" → length 3

### How to Think (Approach)

This is a classic Dynamic Programming problem.

We create a 2D table dp where:
- dp[i][j] = length of LCS using first i characters of S and first j characters of R.Rules:

If the current characters match (S[i-1] == R[j-1]):
- dp[i][j] = dp[i-1][j-1] + 1

If they don’t match:
- dp[i][j] = maximum of (dp[i-1][j], dp[i][j-1])

Base case: dp[0][anything] = 0 and dp[anything][0] = 0 (empty string)

### Step-by-step Logic
- Read T For each test case:
- Read strings S and R
- Let n = length of S, m = length of R
- Create a table dp of size (n+1) × (m+1) and fill with 0
- Fill the table using the rules above
- Answer is dp[n][m]

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


### Time Complexity (TC)
O(T × n × m)

We fill a table of size n × m.

n, m ≤ 100, T ≤ 50 → maximum about 500,000 operations → very fast.

### Space Complexity (SC)

O(n × m)

We use a 2D array of size roughly 100 × 100.

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
