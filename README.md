# 2. 🚚 Move Zeroes — LeetCode 283

### 📌 Problem Statement

Given an integer array `nums`, move all `0`s to the end of the array while maintaining the **relative order of the non-zero elements**.

The array must be modified **in-place** without making a copy of the array.

---

### 🧪 Example 1

```text
Input:
[0, 1, 0, 3, 12]

Output:
[1, 3, 12, 0, 0]
🧪 Example 2
Input:
[0]

Output:
[0]
🎯 Problem Visualization
Before:

[ 0 | 1 | 0 | 3 | 12 ]
  ↑       ↑
 zero    zero


Move all zeroes to the end:

[ 1 | 3 | 12 | 0 | 0 ]

The important rule is that the non-zero elements must keep their original order:

Original:

1 → 3 → 12

Final:

1 → 3 → 12

So this is NOT a sorting problem.

💡 Approach Used

I used a nested-loop approach.

The logic is:

Find a zero
    ↓
Search to the right
    ↓
Find the first non-zero element
    ↓
Swap them
    ↓
Stop searching using break
    ↓
Continue

For example:

[ 0 | 1 | 0 | 3 | 12 ]
  ↑   ↑
  i   j

The first non-zero element after 0 is 1.

Swap:

[ 1 | 0 | 0 | 3 | 12 ]

Then continue:

[ 1 | 3 | 0 | 0 | 12 ]

[ 1 | 3 | 12 | 0 | 0 ]
💻 Solution
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n = nums.size();

        for(int i = 0; i < n; i++) {
            if(nums[i] == 0) {
                for(int j = i + 1; j < n; j++) {
                    if(nums[j] != 0) {
                        swap(nums[i], nums[j]);
                        break;
                    }
                }
            }
        }
    }
};
🔍 Code Explanation
for(int i = 0; i < n; i++)

Traverse the entire array using i.

if(nums[i] == 0)

Check whether the current element is zero.

for(int j = i + 1; j < n; j++)

If it is zero, search the elements to its right.

if(nums[j] != 0)

Find the first non-zero element.

swap(nums[i], nums[j]);

Swap the zero with the non-zero element.

break;

Stop searching after finding the first non-zero element.

📊 Complexity Analysis
Complexity	Value
⏱️ Time Complexity	O(n²)
💾 Space Complexity	O(1)
Why O(n²)?

There are two loops:

Outer loop → O(n)
Inner loop → O(n)

Worst case:

O(n) × O(n) = O(n²)
Why O(1) Space?

The array is modified in-place.

No additional array is created.

Time Complexity  → O(n²)
Space Complexity → O(1)
✅ LeetCode Submission
Metric	Result
🧪 Test Cases	75 / 75 passed
✅ Status	Accepted
⚡ Runtime	46 ms
🏆 Runtime	Beats 5.93%
💾 Memory	23.90 MB
📊 Memory	Beats 55.31%
📅 Submitted	September 24, 2026 — 22:56
📚 What I Learned
✅ How to move zeroes to the end of an array
✅ How to preserve the relative order of non-zero elements
✅ How to find the first non-zero element
✅ How to use swap()
✅ How to use break to stop a loop
✅ How to modify an array in-place
✅ How to analyze time and space complexity
✅ Difference between sorting and moving elements
