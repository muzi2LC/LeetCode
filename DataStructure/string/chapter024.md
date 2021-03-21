## 第一次  
```
class Solution {
public:
    string mergeAlternately(string word1, string word2) {
        string str="";
        if(word1.size()>word2.size())
        {
            for(int i=0;i<word2.size();i++)
            {
                str+=word1[i];
                str+=word2[i];
            } 
            str+=word1.substr(word2.size());  
        }
        else
        {
            string::size_type i=0;
            for(i=0;i<word1.size();i++)
            {
                str+=word1[i];
                str+=word2[i];
            } 
            if(i<word2.size())
                str+=word2.substr(word1.size()); 
        }
        return str;
    }
};

```

## 答案
```
class Solution {
public:
    string mergeAlternately(string word1, string word2) {
        string res;

        for(int i = 0; i < word1.size() || i < word2.size(); i ++){
            if(i < word1.size()) res += word1[i];
            if(i < word2.size()) res += word2[i];
        }

        return res;
    }
};
```
