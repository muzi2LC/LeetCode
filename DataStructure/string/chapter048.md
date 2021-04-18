## 第一次  
```
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
        string res="";
        for(int i=0;i<s.size()-1;i++)
        {
            if(s.size()%(i+1)==0)  
            {
                while(res.size()<s.size())  res+=s.substr(0,i+1);
            }
            if(res==s)  return true;
            else        res="";
        }
        return false;

    }
};
```
