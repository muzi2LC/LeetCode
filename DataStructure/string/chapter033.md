## 第一次  
```
class Solution {
public:
    int maxPower(string s) {
        if(s.empty())   return 0;
        int num=1,maxNum=1;
        char ch=s[0];
        for(int i=1;i<s.size();i++)
        {
            if(ch==s[i])  num++;
            else
            {
                ch=s[i];
                num=1;
            }
             if(num>maxNum)  maxNum=num;
        }
        return maxNum;
    }
};
```
