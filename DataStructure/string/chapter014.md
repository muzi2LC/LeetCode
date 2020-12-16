### 初次提交
```
class Solution {
public:
    int findLUSlength(string a, string b) {
        if(a==b)    return -1;
        int res=0;
        for(int i=0;i<a.size()&&i<b.size();i++ )
        {
            if(a[i]==b[i])
               res++;
        }
        if(res<a.size()&&res<b.size())     return a.size()>b.size()?a.size():b.size();
        if(res==a.size())  return b.size();
        if(res==b.size())  return a.size();
        return res;

    }
};
```

### 优化第一版
```
class Solution {
public:
    int findLUSlength(string a, string b) {
        if(a==b)    return -1;
        return a.size()>b.size()?a.size():b.size();
    }
};
```

### 分析总结
分类讨论：
a==b或者a！=b两种情况。
