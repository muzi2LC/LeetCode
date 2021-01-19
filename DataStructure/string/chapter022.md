## 第一次  
```
class Solution {
public:
    bool arrayStringsAreEqual(vector<string>& word1, vector<string>& word2) {
        string str1="",str2="";
        for(const auto&s:word1)
            str1+=s;
        for(const auto&s:word2)
            str2+=s;
        
        return str1==str2;

    }
};
```
这个提交之后，有时候是0ms，有时候是4ms，有时候是8ms   
##答案
```
class Solution {
public:
    bool arrayStringsAreEqual(vector<string>& word1, vector<string>& word2) {
        int i = 0,j = 0,ci = 0,cj = 0;
        while(ci < word1.size() && cj < word2.size()){
            if(word1[ci][i] == word2[cj][j]){
                i++;
                j++;
            }else{
                return false;
            }
            if(i == word1[ci].size()){
                ci++;
                i = 0;
            }
            if(j == word2[cj].size()){
                cj++;
                j = 0;
            }
        }
        if(i+j == 0){
            return true;
        }else{
            return false;
        }
    }
};
```
##总结  
本人的答案虽然有两层循环，但是比起一层循环来说，时间复杂度都是o（kN），其中k为常数。更加简洁明了。
