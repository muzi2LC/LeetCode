## 自己尝试：  
### 第一版
```
class Solution {
public:
    int maxDepth(string s) {
        stack<char> stk;
        size_t i = 0;
        if (s.empty()) return 0;
        for (char ch : s)
        {
            if (stk.size() > i)      i = stk.size();
            if (ch == ')')
            {
                if (stk.empty())     return 0;
                else                 stk.pop();
            }
            if (ch == '(')           stk.push(ch);
        }
        return i;
    }
};
```
###第二版
string可以直接在其源字符串上修改
```
class Solution {
public:
    string toLowerCase(string str) {
        if(str.empty())  return "";
        for(size_t i=0;i<str.size();i++)
        {
            if(str[i]>='A'&&str[i]<='Z')
                 str[i]=str[i]+32;
        }
        return str;
    }
};
```
## 查看答案

```
class Solution {
public:
    string toLowerCase(string str) {
        for(auto& ch:str){
            ch|=32;
        }
        return str;
    }
};
```

## 分析总结
string是一个变量，类似数组可以直接赋值改变其元素值。
答案是比较巧妙的一种解法，可打印字符从33-127,33-63与32求按位或仍旧为原来的数值，64-95与32求按位或，相当于增加32，对于96-127位求按位或，实际上是不变的；
所以如果限定了字符串中的字符为‘A’-‘Z’和‘a’-‘z’，这个代码是成立的，但是题目中没有很明确的说明。

## 另外笔记：
 位运算
  大写变小写、小写变大写 : 字符 ^= 32;
  大写变小写、小写变小写 : 字符 |= 32;  
  小写变大写、大写变大写 : 字符 &= -33;
  eg：
  65(A)->二进制表示为100 0001
  32的二进制表示为 010 0000 
  100 0001|010 0000=110 0001->97(a)

