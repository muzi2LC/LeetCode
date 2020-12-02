## 自己尝试：  
### 代码：
```
class Solution {
public:
    void reverseString(vector<char>& s) {
        char ch;
        for(int i=0;i<s.size()/2;i++)
        {
            ch=s[s.size()-1-i];
            s[s.size()-1-i]=s[i];
            s[i]=ch;   
        }    
    }
};
```
###  查看答案
```
class Solution {
public:
    void reverseString(vector<char>& s) {
        int n=s.size();
        for(int low=0,high=n-1;low<high;low++,high--)
        {
                swap(s[low],s[high]);
        }
    }
};
```

### 分析总结
这一道题的思路其实很简单，交换一下即可。主要需要学习的是交换操作的处理。有时候可以按位运算来处理。 参考[位运算小技巧](bit_tips.md)
