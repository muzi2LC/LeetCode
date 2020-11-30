## 自己尝试：  
```
class Solution {
public:
    bool judgeCircle(string moves) {
        int k=0,i=0;
        for(char ch:moves)
        {
            if(ch=='L') i++;
            if(ch=='R') i--;
            if(ch=='U') k++;
            if(ch=='D') k--;    
        }
        return i==0&&k==0;
    }
};
```

## 查看题解：  

```
class Solution {
public:
    bool judgeCircle(string moves) {
       int left=0;
       int right=0;
       int up=0;
       int down=0;
       for(int i=0;i<moves.size();i++)
       {
          if(moves[i]=='R')
          {
              right++;
          }
         else if(moves[i]=='L')
          {
             left++;
          }
         else if(moves[i]=='U')
          {
              up++;
          }
          else
              down++;
       }
     if(up==down&&right==left)
     return true;
     return false;
    }
};
```
## 分析总结  
答案做的没我好！
