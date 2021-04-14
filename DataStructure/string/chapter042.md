## 第一次  
```
class Solution {
public:
    string makeGood(string s) {
        if(s.size()==0||s.size()==1)   return s;
        string res;
        for(int i=0;i<s.size();i++)
        {
            if(res.empty()) res+=s[i];
            else if(isBad(res[res.size()-1],s[i]))  res.erase(res.size()-1);
            else                                    res+=s[i];
        }
        return res;    
    }
    bool isBad(char ch1,char ch2)
    {
        if(abs(ch1-ch2)==32)  return true;
        return false;
    }
};
```
