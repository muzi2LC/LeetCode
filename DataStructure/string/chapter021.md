### 初次提交
```
class Solution {
public:
    int rotatedDigits(int N) {
        int res=0;
        for(int i=1;i<=N;i++)
        {
            if(isGood(i))   res++;
        }
        return res;
    }
    bool isGood(int num)
    {
        int n=num;
        string s="";
        while(n)
        {
            int k=n%10;
            char ch=k+'0';
            n=n/10;
            s=ch+s;   
        }
        int res=0;
        for(int i=0;i<s.size();i++)
        {
            int c=0;
            if(s[i]=='3'||s[i]=='4'||s[i]=='7')  return false;
            if(s[i]=='0'||s[i]=='1'||s[i]=='8')  c=s[i]-'0';
            if(s[i]=='2')    c=5;
            if(s[i]=='5')    c=2;
            if(s[i]=='6')    c=9;
            if(s[i]=='9')    c=6;
            res=res*10+c;
        }
        if(res==num)     return false;
        else             return true;
    }
};
```
时间复杂度有待改善，isGood（）应该可以只经过一次循环  
### 再次提交
```
class Solution {
public:
    int rotatedDigits(int N) {
        int res=0;
        for(int i=1;i<=N;i++)
        {
            if(isGood(i))   res++;
        }
        return res;
    }
    bool isGood(int num)
    {
        int n=num;
        int res=0;
        int i=0;
        while(n)
        {
            int k=n%10;
            if(k==3||k==4||k==7)     return false;
            else if(k==2)      k=5;
            else if(k==5)      k=2;
            else if(k==6)      k=9;
            else if(k==9)      k=6;
            n=n/10;
            res=k*pow(10,i)+res;  
            i++;
        }
        if(res==num)     return false;
        else             return true;
    }
};
```
这个版本是要经过两次遍历。看了一下答案说是要动态规划
### 最终版本




