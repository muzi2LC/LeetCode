### 初次提交
```
class Solution {
public:
    int countMatches(vector<vector<string>>& items, string ruleKey, string ruleValue) {
        int i=0,num=0;
        if(ruleKey=="type")           i=0;
        else if(ruleKey=="color")     i=1;
        else if(ruleKey=="name")      i=2;
        else                          return 0;
        if(items.empty())     return 0;
        else{
            for(int k=0;k<items.size();k++)
               if(items[k][i]==ruleValue)  
                     num++;
        }
        return num;
    }
};

```





