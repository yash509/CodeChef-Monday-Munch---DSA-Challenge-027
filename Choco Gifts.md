### Problem
A chocolate shop prepares large boxes (4 chocolates) and small boxes (2 chocolates).

Given N chocolates (N is even), the shop makes as many large boxes as possible and then uses the remaining chocolates for small boxes.

Check whether at least one small box is prepared.

**Input**
- First line: T
- Each test case: one integer N

**Output**
YES if at least one small box is made, otherwise NO.

**Constraints**

- 1 ≤ T ≤ 100
- 2 ≤ N ≤ 1000
- N is even

### Explanation
After filling maximum number of boxes of size 4, the remainder is N % 4.

**Because N is even, the remainder can only be 0 or 2.**
- Remainder 2 → one small box is made → YES
- Remainder 0 → no small box → NO

**Dry Run**
- 14 → 14 % 4 = 2 → YES
- 20 → 20 % 4 = 0 → NO
- 2  → 2 % 4 = 2 → YES
- 26 → 26 % 4 = 2 → YES

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
        int N;
        cin >> N;
        
        if (N % 4 == 2) {
            cout << "YES\n";
        } else {
            cout << "NO\n";
        }
    }
    
    return 0;
}
