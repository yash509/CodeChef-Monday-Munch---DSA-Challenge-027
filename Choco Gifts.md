### Problem
A chocolate shop prepares large boxes (4 chocolates) and small boxes (2 chocolates).

Given N chocolates (N is even), the shop makes as many large boxes as possible and then uses the remaining chocolates for small boxes.

Check whether at least one small box is prepared.

### Problem in Simple Words

We have N chocolates (N is always even).

We first make as many boxes of 4 chocolates as possible.

Whatever chocolates are left, we use them to make boxes of 2 chocolates.

Question: Will we be able to make at least one box of 2 chocolates?


### How to Think (Approach)

When we divide N by 4, the remainder tells us how many chocolates are left.Because N is even, the possible remainders are only:
0 → nothing left → no small box
2 → exactly 2 left → one small box
So we only need to check:

If N % 4 == 2 → YES

Else → NO

### Step-by-step Logic
- Read T
- For each test case:
- Read N
- Calculate N % 4
- If remainder is 2 → YES
- Else → NO

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
- N = 14 → 14 ÷ 4 = 3 boxes (12 chocolates), remainder 2 → YES
- N = 20 → 20 ÷ 4 = 5 boxes, remainder 0 → NO
- N = 2  → 0 large boxes, remainder 2 → YES
- N = 26 → 6 large boxes (24), remainder 2 → YES

### Time Complexity (TC)

O(T)

Constant work per test case.

### Space Complexity (SC)O(1)

Only a few variables used.

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
