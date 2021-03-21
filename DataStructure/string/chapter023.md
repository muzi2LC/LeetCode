## 第一次  
```
class Solution {
public:
    int countConsistentStrings(string allowed, vector<string>& words) {
        int num=0;
        for(int i=0;i<words.size();i++)
        {
            int j=0;
            while(j!=words[i].size())
            {
                if(allowed.find(words[i][j])==string::npos)  break;
                else  j++;
            }
            if(j==words[i].size())  num++;
        }
        return num;
    }
};

```
##  答案
```
class Solution {
public:
    int countConsistentStrings(string allowed, vector<string>& words) {
        int allowed_map[27] = {0};
        for(char ch : allowed) {
            allowed_map[ch - 'a'] = 1;
        }

        int sum = 0;
        for(string word : words) {
            sum += 1;
            for(char ch : word) {
                if(allowed_map[ch - 'a'] != 1) {
                    sum -= 1;
                    break;
                }
            }
        }
        return sum;
    }
};
```
## 分析
string::find 的时间复杂度为o(m*n) 与map的查找时间复杂度为o（lg(n）)  
参考：http://www.cplusplus.com/reference/string/basic_string/find/ 和 http://www.cplusplus.com/reference/map/map/operator[]/
