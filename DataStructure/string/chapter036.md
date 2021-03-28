## 第一次  
```
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
        if(ransomNote.empty()&&magazine.empty())     return true;
        if(ransomNote.size()>magazine.size())        return false;
        int R[26]={0};
        int M[26]={0};
        for(int i=0;i<ransomNote.size();i++)
        {
            R[ransomNote[i]-'a']++;
        }
        for(int i=0;i<magazine.size();i++)
        {
            M[magazine[i]-'a']++;
        }
        for(int i=0;i<26;i++)
        {
            if(R[i]>M[i])  return false;
        }
        return true;
    }
};
```
