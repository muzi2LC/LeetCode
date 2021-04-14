## 第一次  
```
class Solution {
public:
    bool checkRecord(string s) {
        int numA=0;
        for(int i=0;i<s.size();i++)
        {
            if(i<s.size()-2)
            {
                if(s[i]=='L'&&s[i]==s[i+1]&&s[i]==s[i+2])  return false;
            }
            if(s[i]=='A')  numA++;
            if(numA>1)   return false;
        }
        return true;
    }
};

```
