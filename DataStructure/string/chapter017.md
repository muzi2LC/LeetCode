### 初次提交
```
class Solution {
public:
    int maxNumberOfBalloons(string text) {
        int min; 
        int bi=0,ai=0,li=0,oi=0,ni=0;
        for(char ch:text)
        {
            if(ch=='b')
                bi++;
            if(ch=='a')
               ai++;
            if(ch=='l')
               li++;
            if(ch=='o')
               oi++;    
            if(ch=='n')
               ni++;       
        }
        ai=ai<bi?ai:bi;
        ai=ai<ni?ai:ni;
        li=li<oi?li:oi;
        min=li/2<ai?li/2:ai;
        return min;
    }
};
```
### 查看答案
```
class Solution {
public:
    int maxNumberOfBalloons(string text) {
        int map[26] = {0}, ans = INT_MAX;
        for (auto c:text)
            map[c-'a']++;
        ans = min(ans, map[0]);
        ans = min(ans, map[1]);
        ans = min(ans, map[11]/2);
        ans = min(ans, map[13]);
        ans = min(ans, map[14]/2);
        return ans;
    }
};
```


