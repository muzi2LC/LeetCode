## 第一次  
```
class Solution {
public:
    string countAndSay(int n) {
        if(n<1) return "";
        int i=1;
        string str="1";
        while(i<n)
        {
            getNewStr(str);
            i++;
        }
        return str;
    }
    void getNewStr(string &str)
    {
        char chCur=str[0];
        int num=1;
        string res="";
        for(int i=1;i<str.size();i++)
        {
            if(chCur==str[i]) num++;
            else
            {
                res=res+char('0'+num)+char(chCur);
                chCur=str[i];
                num=1;
            }
        }
        if(chCur==str[str.size()-1])
        {
             res=res+char('0'+num)+char(chCur);
        }
        str=res;
    }
};

```
## 答案  
```
class Solution {
public:
    void work(string &s, int cnt, char c){
        s += (char)(cnt + '0');
        s+=c;
    }
    void func(string &s1, string &s2){
        int cnt = 0;
        for (int i = 0; i < s1.size(); i++){
            if (cnt == 0 || s1[i] == s1[i - 1]){
                cnt++;
            }else{
                work(s2, cnt, s1[i-1]);
                cnt = 1;
            }
        }
        work(s2, cnt, s1[s1.size() - 1]);
    }
    string countAndSay(int n) {
        string ans[2] = {"", "1"};
        int a = 0, b = 1;
        for (int i = 2; i <= n; i++){
            ans[a].clear();
            func(ans[b], ans[a]);
            swap(a, b);
        }
        return ans[b];
    }
};
```

## 分析  
实际上跟答案的算法是一样的，只是中间的细节操作可能有些不同。但是执行起来时间有点长!!
