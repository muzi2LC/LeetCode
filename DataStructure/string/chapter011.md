### 初次提交
```
class Solution {
public:
    string reverseWords(string s) {
        string res="";
        stack<char> stk;
        for(int i=0;i<s.size();i++)
        {
            if(s[i]!=' ')
              stk.push(s[i]);
            else
            {
                while(!stk.empty())
                {
                    res+=stk.top();
                    stk.pop();
                }
                 res+=' ';
            }
        }
        while(!stk.empty())
        {
            res+=stk.top();
            stk.pop();
        }
        return res;
    }
};
```
时间和空间性能不太好，累计遍历两次字符串。空间上加了一个栈。

### 查看答案  
作者：[LeetCode-Solution](https://leetcode-cn.com/problems/reverse-words-in-a-string-iii/solution/fan-zhuan-zi-fu-chuan-zhong-de-dan-ci-iii-by-lee-2/)  
```
class Solution {
public: 
    string reverseWords(string s) {
        int length = s.length();
        int i = 0;
        while (i < length) {
            int start = i;
            while (i < length && s[i] != ' ') {
                i++;
            }

            int left = start, right = i - 1;
            while (left < right) {
                swap(s[left], s[right]);
                left++;
                right--;
            }
            while (i < length && s[i] == ' ') {
                i++;
            }
        }
        return s;
    }
};
```
### 分析总结  
理论上时间复杂度应该是一样的,为O(n)，空间复杂度作者是O(1)，本人是O(n);  
这道题需要学习的是本地交换操作，为了减少空间消耗，很多题目都有类似操作。  
总体来说，思路都是先找到空格符号，然后处理每个单词。
