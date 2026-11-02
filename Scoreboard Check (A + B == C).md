### Problem
A game has two rounds. A player scores A points in the first round and B points in the second round. The scoreboard displays C as the total score.  
Determine whether the displayed total is correct.

**Input**
- First line: T (number of test cases)
- Each test case: three integers A B C

**Output**
For each test case print YES if A + B == C, otherwise NO.

**Constraints**
- 1 ≤ T ≤ 100
- 0 ≤ A, B, C ≤ 100

### Explanation
For every test case simply check whether the sum of the first two numbers equals the third number.

**Dry Run**
- 12 8 20 → 12 + 8 = 20 → YES
- 7 6 12 → 7 + 6 = 13 ≠ 12 → NO
- 0 15 15 → 0 + 15 = 15 → YES
- 50 60 100 → 50 + 60 = 110 ≠ 100 → NO

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
        int A, B, C;
        cin >> A >> B >> C;
        
        if (A + B == C) {
            cout << "YES\n";
        } else {
            cout << "NO\n";
        }
    }
    
    return 0;
}
