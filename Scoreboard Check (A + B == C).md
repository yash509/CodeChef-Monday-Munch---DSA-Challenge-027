### Problem
A game has two rounds. A player scores A points in the first round and B points in the second round. The scoreboard displays C as the total score.  
Determine whether the displayed total is correct.

### Problem in Simple Words
You are given three numbers A, B and C.  
You have to check if A + B is equal to C or not.  
There will be many such test cases.

### How to Think (Approach)
This is the simplest kind of problem.
- Read how many test cases there are (T).
- For each test case, read three numbers.
- Add the first two numbers.
- If the sum is exactly equal to the third number → print YES
- Otherwise → print NO

No special algorithm is needed. Just basic addition and comparison.

**Input**
- First line: T (number of test cases)
- Each test case: three integers A B C

**Output**
For each test case print YES if A + B == C, otherwise NO.

**Constraints**
- 1 ≤ T ≤ 100
- 0 ≤ A, B, C ≤ 100

### Step-by-step Logic
1. Read T
2. Repeat T times:
   - Read A, B, C
   - Calculate sum = A + B
   - If sum == C → YES
   - Else → NO

### Explanation
For every test case simply check whether the sum of the first two numbers equals the third number.

**Dry Run**
- 12 8 20 → 12 + 8 = 20 → YES
- 7 6 12 → 7 + 6 = 13 ≠ 12 → NO
- 0 15 15 → 0 + 15 = 15 → YES
- 50 60 100 → 50 + 60 = 110 ≠ 100 → NO

### Time Complexity (TC)
O(T)  
Because we do constant work for each of the T test cases.  
Since T ≤ 100, it is extremely fast.

### Space Complexity (SC)
O(1)  
We only use a few integer variables. No extra arrays or data structures.

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
