Accepted
75 / 75 testcases passed
pranavpatil1012553
pranavpatil1012553
submitted at Sep 24, 2026 22:56

Analysis
Sync w/ LeetHubManually upload this submission to GitHub (beta).
This will OVERWRITE your current submission.
Please be mindful of your GitHub rate-limits.

Solution
1024
👑 Unlock the Full LeetCode Experience
Company problems, Ask Leet, and expert editorials — all in one plan.
Runtime
46
ms
Beats
5.93%
Memory
23.90
MB
Beats
55.31%
Code
C++
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
View more
 
More challenges
