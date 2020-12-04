### 初次提交
```
class Solution {
public:
    string generateTheString(int n) {
        if(n<=0)  return "";
        string str;
        if(n%2==1)
        {
            for(int i=0;i<n;i++)
               str+='a';
        }
        else
        {
            for(int i=0;i<n-1;i++)
               str+='a';
            str+='b';
        }
        return str;
    }
};
```
### 优化一下：
```
class Solution {
public:
    string generateTheString(int n) {
        if(n<=0)  return "";
        string str;
        if(!(n&1))
        {
            n--;
            str+='a';
        }
        for(int i=0;i<n;i++)
           str+='b';
        return str;
    }
};
```
