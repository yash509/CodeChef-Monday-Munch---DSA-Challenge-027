### Problem
There are N players with power levels A1, A2, …, AN.

A player earns a badge if the number of players with power ≤ his/her power (including himself) is strictly greater than the number of players with higher power.

Find how many players earn a badge.

**Input**
- First line: T
- For each test case:
- First line: N
- Second line: N integers Ai

**Output**
For each test case print the number of players who earn a badge.

**Constraints**
- 1 ≤ T ≤ 1000
- 1 ≤ N ≤ 100
- 0 ≤ Ai ≤ 100

**Explanation**
- N is at most 100, so a simple O(N²) approach is fine.
- For every player count how many values are ≤ his power and how many are greater.
- If (≤ count) > (greater count) he gets a badge.

**Dry Run (Sample 1):**

**Array: [4, 1, 4, 2, 5]**

- Power 4 → ≤ = 4, > = 1 → badge
- Power 1 → ≤ = 1, > = 4 → no
- Power 4 → ≤ = 4, > = 1 → badge
- Power 2 → ≤ = 2, > = 3 → no
- Power 5 → ≤ = 5, > = 0 → badge

Total = 3

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
        
        vector<int> A(N);
        for (int i = 0; i < N; i++) {
            cin >> A[i];
        }
        
        int badgeCount = 0;
        
        for (int i = 0; i < N; i++) {
            int lessOrEqual = 0;
            int higher = 0;
            
            for (int j = 0; j < N; j++) {
                if (A[j] <= A[i]) lessOrEqual++;
                else higher++;
            }
            
            if (lessOrEqual > higher) {
                badgeCount++;
            }
        }
        
        cout << badgeCount << "\n";
    }
    
    return 0;
}
