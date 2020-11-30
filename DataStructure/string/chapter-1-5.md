## 自己尝试：  
有两个元素，很容易就学会用map；
```
class Solution {
public:
    string destCity(vector<vector<string>>& paths) {
        map<string,string> path;
        for(auto ve:paths)
        {
            path[ve[0]]=ve[1];
        }
        string str=paths[0][0];
        while(path[str]!="")
            str=path.at(str);
        return str;
    }
};
```

## 查看题解：  

```
class Solution {
public:
    string destCity(vector<vector<string>>& paths) {
        map<string, int> helper;
        for(auto p:paths){
            helper[p[0]] += 1;
            helper[p[1]] += 0;
        }
        for(auto h:helper){
            if(h.second == 0){
                return h.first;
            }
        }
        return "";
    }
};
```

## 分析总结：和最快的答案一样经过两次遍历。就时间复杂度而言是一样的。不断提交发现运行时间不断变化。本人答案相对直观一些，但标准答案很巧妙。
