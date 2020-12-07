## 自己尝试：  
```
class Solution {
public:
    int maxLengthBetweenEqualCharacters(string s) {
        int a[26];
        int b[26];
        memset(a,-1,sizeof(a));
        memset(b,-1,sizeof(b));
        for(int j=0;j<s.size();j++)
        {
            int i=s[j]-'a';
            if(a[i]==-1)   a[i]=j;
            else
            {
                if(j>b[i]) b[i]=j;
            }
        }
        int max=-1;
        for(int i=0;i<26;i++)
        {
            if(b[i]!=-1) 
            {
                if(max<b[i]-a[i])  max=b[i]-a[i];
            }
        }
        if(max!=-1) max-=1;
        return max;
    }
};
```

## 查看题解：  
```
class Solution {
public:
    int maxLengthBetweenEqualCharacters(string s) {
        int start[26];
        int res= -1;
        fill_n(&start[0],26,-1);
        for(int i=0;i<s.size();++i)
        {
            if(start[s[i]-'a']==-1)
                start[s[i]-'a']=i;
            else
                res = max(res,i-start[s[i]-'a']-1);
        }
        return res;
    }
};
```
## 分析总结
这道题其实我和最佳答案的思路是一样的，只不过本人答案有优化的空间。需要学习的是，可以用数组来映射26个字母表，这样就不需要用到map。
