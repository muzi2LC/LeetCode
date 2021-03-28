## 第一次  
```
class Solution {
public:
    bool detectCapitalUse(string word) {
        if(word.empty())  return true;
        int num=0;
        for(int i=0;i<word.size();i++)
        {
            if(isupper(word[i])) num++;
        }
        if(num==word.size()||num==0)  return true;
        if(num==1&&isupper(word[0]))  return true;
        return false;
    }
    
};

```
