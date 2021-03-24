## 第一次  
```
class Solution {
public:
    string longestNiceSubstring(string s) {
        string res="";
        for(int i=0;i<s.size();i++)
        {
            string str="";
            for(int j=i+1;j<s.size();j++)
            {
                if(isNice(s,i,j)) str=s.substr(i,j-i+1);
            }
            if(res.size()<str.size())  res=str;
        }
        return res;
    }
    bool isNice(string s,size_t i,size_t j)
    {
        int A[26]={0};
        int a[26]={0};
        for(size_t k=i;k<j+1;k++)
        {
            if(s[k]-'A'<26)  A[s[k]-'A']++;
            else             a[s[k]-'a']++;
        }
         for (int i = 0; i < 26; ++i) {
            if ((a[i] > 0 && A[i] <= 0)||(a[i] <= 0 && A[i] > 0)) return false;
        }
        return true;
    }
};
```
## 答案
```
class Solution {
public:
    string longestNiceSubstring(string s) {
        string ans;
        
        for(int i = 0; i < s.length(); i++){
            int a = 0, b = 0;
            for(int j = i; j < s.length(); j++){
                if(isupper(s[j])){
                    a |= 1 << (s[j] - 'A');
                }else{
                    b |= 1 << (s[j] - 'a');
                }
                if(a == b && j - i + 1> ans.length()){
                    ans = s.substr(i,j - i + 1);
                }
            }
        }
        return ans;
    }
}; 
```


