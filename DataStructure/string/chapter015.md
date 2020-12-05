不太会，直接查看答案

### 查看答案

作者：[Gary_coding](https://leetcode-cn.com/problems/remove-palindromic-subsequences/solution/c-zhong-gui-zhong-ju-de-0msjie-fa-bao-li-by-gary-4/)

```
class Solution {
public:
    int removePalindromeSub(string s) {
        if (s.empty()) return 0;
        string tmp = s;
        reverse(s.begin(), s.end());
        if (s == tmp) return 1;
        return 2;
    }
};
```
搞了半天是个脑筋急转弯  
回文子序列不是回文子字符串，序列意味着不需要回文不需要连续。所以可以先删除a，再删除b即可。


