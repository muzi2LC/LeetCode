## 第一次  
```
class Solution {
public:
    int firstUniqChar(string s) {
        int a[26]={0};
        string res="";
        for(int i=0;i<s.size();i++)
        {
            a[s[i]-'a']++;
        }
        for(int i=0;i<26;i++)
        {
            if(a[i]==1)  res+=char(i+'a');
        }
        for(int i=0;i<s.size();i++)
        {
            if(res.find(s[i])!=string::npos)  return i;
        }
        return -1;
    }
};
```
### VS C++中非0即为真
## 第一次  
```
class Solution {
public:
    int firstUniqChar(string s) {
        int a[26]={0};
        for(int i=0;i<s.size();i++)
        {
            a[s[i]-'a']++;
        }
        for(int i=0;i<s.size();i++)
        {
            if(a[s[i]-'a']==1)  return i;
        }
        return -1;
    }
};
```

