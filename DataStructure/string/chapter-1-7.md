## 直接看答案
```
class Solution {
public:
    int uniqueMorseRepresentations(vector<string>& words) {
        // 哈希表法
        int len = words.size();
        if(len == 0){
            return 0;
        }
        vector<string> datas = {".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."};
        unordered_set<string> tag;
        for(int i = 0; i < len; i ++){
            string str;
            for(int j = 0; j < words[i].size(); j ++){
                char ch = words[i][j];
                if(ch >= 'a' && ch <= 'z'){
                    str += datas[ch - 'a'];
                }else if(ch >= 'A' && ch <= 'Z'){
                    str += datas[ch - 'A'];
                }else{
                    return -1;
                }
            }
            tag.insert(str);
        }
        return tag.size();
    }
};
```
## 分析总结  
主要是忘记了C++中还有set的集合。这道题一开始将字符转换为摩斯密码，我想到的是用map，但是由于是由顺序的集合，用数组+做差的形式更简便。
