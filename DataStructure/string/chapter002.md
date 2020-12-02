## 自己尝试：  
### 代码：
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
### 执行结果：  
执行结果：通过  
显示详情  
执行用时：0 ms, 在所有 C++ 提交中击败了100.00%的用户  
内存消耗：6.4 MB, 在所有 C++ 提交中击败了24.23%的用户  

### 修改第一版  
思考：使用stack数据结构是我在邓俊辉老师《数据结构》一书中看到的想法，主要是用来判断括号输入是否有效。这道题要优化内存消耗，必然不能用stack，
注意到题目描述中表示输入的字符串都是有效字符串，也就是说，括号的输入默认是正确的，所以去掉stack数据结构。
```
class Solution {
public:
    int maxDepth(string s) {
         size_t cout = 0;
	       size_t k = 0;
	       for (size_t i = 0; i < s.size(); i++)
	       {
		       if (s[i] == '(')
			          k++;
	       	if (s[i] == ')')
		          	k--;
	      	if (k > cout)
			     cout = k;
			
       	}
	    return cout;
    }
};
```
提交之后，发现仍然达不到要求，考虑到有两个size_t,尝试把其中一个删除掉。但是仍旧没有作用。

### 修改第二版
```
class Solution {
public:
    int maxDepth(string s) {
	int cout=0;
	for (size_t i = 0; i < s.size(); i++)
	{
        if (i > cout)
			cout = i;
		if (s[i] != '(')
		{
            if (s[i] == ')')     {s.erase(s.begin() + i);    s.erase(s.begin()+i-1);i-=2;}
			else                 {s.erase(s.begin() + i);    i--;}
		}
	}
	return cout;
    }
};
```
无效，看答案。。。。

## 查看答案
## mark有一个疑问
  答案跟我修改的第一版一样，将答案提交之后，发现空间利用率跟我的一样。
  
```
class Solution {
public:
    int maxDepth(string s) {
        int max = -1;
        int depth = 0;
        for(auto v:s)
        {
            if(v=='(')
            {
                depth++;    
            }
            else if(v==')')
            {
                depth--;
            }
            if(depth>max)
                max = depth;
        }
        return max;
    }
};
```
