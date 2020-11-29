## 这道题不太会，直接看的题解
```
class Solution {
public:
    string sortString(string s) {
        int ary[26] = { 0 };
        for (char ch : s){
		ary[ch - 'a']++;
        }
        string ret;
        while (s.size()!=ret.size()){
            for (int i = 0; i < 26; i++)
                if (ary[i]){
                    ret += i + 'a';
                    ary[i]--;
                    }
            for (int i = 25; i > -1; i--)
                if (ary[i]){
                    ret += i + 'a';
                    ary[i]--;
                }
		}
        return ret;   
    }
};
```
