## 第一次  
```
class Solution {
public:
    string reformatNumber(string number) {
        string str="",str2="";
        for(int i=0;i<number.size();i++)
        {
            if(number[i]!=' '&&number[i]!='-')   str+=number[i];
        }
        if(str.size()%3!=1)
        {
            for(int i=0;i<str.size();i++)
            {
                str2+=str[i];
                if(i%3==2&&i!=str.size()-1)    str2+='-';
            }
        }
        else
        {
            int i=0;
            for(i=0;i<str.size()-4;i++)
            {
                str2+=str[i];
                if(i%3==2)    str2+='-';
                
            }
            str2+=str[i];
            str2+=str[i+1];
            str2+="-";
            str2+=str[i+2];
            str2+=str[i+3];
        }
        return str2;
    }
};
```

## 答案 
```
class Solution {
public:
    string reformatNumber(string number) {
        string str, res;
        for (auto &s : number) {
            if (s != ' ' && s != '-') str += s;
        }
        
        res += str[0];
        for (int i = 1; i < str.size(); ++i) {
            if (i % 3 == 0) res += '-';
            res += str[i];
        }
        
        if (res[res.size() - 2] == '-') swap(res[res.size() - 2], res[res.size() - 3]); 
        return res;
    }
};
```
## 分析   
这里需要注意的事字符串的存储方式:字符串存在堆上，以字符数组的形式存在。swap函数传入的事两个地址的数值。
