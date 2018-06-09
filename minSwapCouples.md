# Practice
Couples Holding Hands
## 问题分析：
#### 
N couples sit in 2N seats arranged in a row and want to hold hands. We want to know the minimum number of swaps so that every couple is sitting side by side. A swap consists of choosing any two people, then they stand up and switch seats.
The people and seats are represented by an integer from 0 to 2N-1, the couples are numbered in order, the first couple being (0, 1), the second couple being (2, 3), and so on with the last couple being (2N-2, 2N-1).
The couples' initial seating is given by row[i] being the value of the person who is initially sitting in the i-th seat.
## Note:
len(row) is even and in the range of [4, 60].
row is guaranteed to be a permutation of 0...len(row)-1.
## 编程实现：
```C++
class Solution {
public:
    int minSwapsCouples(vector<int>& row) {
        int n = row.size();
        for (int i = 0; i < n; i++) {
            row[i] -= row[i] % 2;
        }
        int ans = 0;
        for (int i = 0; i < n; i += 2) {
            if (row[i] == row[i + 1]) {
                continue;
            }
            for (int j = i + 2; j < n; j++) {
                if (row[i] == row[j]) {
                    ans++;
                    swap(row[i + 1], row[j]);
                    break;
                }
            }
        }
        return ans;
    }
};
```
## 总结体会：
考虑到对于row[0]来说，如果row[1] 和 row[0]是夫妻，那么他们两个就都不动就好.如果两个都移走，那么不是最优.如果考虑row[0]和row[1]不是夫妻的情况，我们把row[1]和row[0]的夫妻交换.从row[0]开始，每次找到对应的夫妻，放在其边上就好.