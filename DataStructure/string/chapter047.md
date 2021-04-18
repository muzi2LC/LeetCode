## 第一次  
```
class Solution {
public:
    string reformat(string s) {
        string num="",str="";
        for(int i=0;i<s.size();i++)
        {
            if(s[i]>='a'&&s[i]<='z')   str+=s[i];
            if(s[i]>='0'&&s[i]<='9')   num+=s[i];
        }
        if(str.size()+1<num.size())  return "";
        if(str.size()>num.size()+1)  return "";
        s="";
        for(int i=0;i<num.size()&&i<str.size();i++)
        {
            s=s+num[i];
            s=s+str[i];
        }
        if(str.size()<num.size())  s=s+num.back();
        if(num.size()<str.size())  s=str.back()+s;
        return s;
    }
};
```
### 时间过长 内存消耗过多 但就答案来说，实际思想是一一致。时间复杂度应该是一样的。
