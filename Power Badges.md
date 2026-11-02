### Problem
There are N players with power levels A1, A2, …, AN.

A player earns a badge if the number of players with power ≤ his/her power (including himself) is strictly greater than the number of players with higher power.

Find how many players earn a badge.

### Problem in Simple Words

There are N players, each has a power number.

For a player to get a badge:
Count how many players have power ≤ his power (include himself)
Count how many players have power > his power
If the first count is strictly greater than the second count → he gets a badge
We need to find how many players get a badge.

### How to Think (Approach)

N is very small (maximum 100).

So we can afford to check every player one by one.For each player:
Loop through all players again
Count how many have ≤ power and how many have > power
Check the condition
This is a simple nested loop (brute force) approach.

### Step-by-step Logic
- Read T
- For each test case:
- Read N
- Read the array of N powers
- Initialize badgeCount = 0
- For every player i:
- lessOrEqual = 0, higher = 0
- For every player j:
- if A[j] ≤ A[i] → lessOrEqual++
- else → higher++
- if lessOrEqual > higher → badgeCount++
- Print badgeCount

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


- Player 0 (power 4):
- ≤ → 4,1,4,2 (4 players), > → 5 (1 player) → 4 > 1 → badge

- Player 1 (power 1):
- ≤ → only 1 (1 player), > → 4 players → 1 > 4? No

- Player 2 (power 4): same as player 0 → badge

- Player 3 (power 2):
- ≤ → 1,2 (2 players), > → 3 players → 2 > 3? No

- Player 4 (power 5):
- ≤ → all 5, > → 0 → 5 > 0 → badge

Total badges = 3

### Time Complexity 

O(T × N × N) = O(T × N²)

Because for each of the N players we scan all N players.

N ≤ 100, T ≤ 1000 → maximum operations ≈ 10 million → easily accepted.

### Space Complexity 

O(N)

We store the array of N powers. Extra variables are constant.

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
