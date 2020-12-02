## 自己尝试：  
一开始就是想直接从后面出发，比较适合，然后就是解决数字到字母的映射，这里注意，所有的顺序字符互相转化，可以利用加减法作映射。最后作一个顺序转化。

### 代码：
```
class Solution {
public:
    string freqAlphabets(string s) {
        string resN="",res="";
        if(s.empty())  return "";
        for(int i=s.size()-1;i>=0;i--)
        {
            if(s[i]=='#')
            {
                resN+=(s[i-2]-'0')*10+(s[i-1]-'1')+'a';
                i=i-2;
            }
            else
            {
                resN+=(s[i]-'1')+'a';
            }
        }
        for(int i=resN.size()-1;i>=0;i--)
            res+=resN[i];
        return res;
    }
};
```
## 查看答案 
```
class Solution {
public:
    string freqAlphabets(string s) {
        string ret;
        for(int i=0;i<s.length();)
        {
            if(i+2<s.length()&&s[i+2]=='#')
            {
                if((s[i]-48)==1)
                {
                    switch(s[i+1]-48)
                    {
                        case 0:ret+="j";break;
                        case 1:ret+="k";break;
                        case 2:ret+="l";break;
                        case 3:ret+="m";break;
                        case 4:ret+="n";break;
                        case 5:ret+="o";break;
                        case 6:ret+="p";break;
                        case 7:ret+="q";break;
                        case 8:ret+="r";break;
                        case 9:ret+="s";break;
                    }
                }
                else if((s[i]-48)==2)
                {
                    switch(s[i+1]-48)
                    {
                        case 0:ret+="t";break;
                        case 1:ret+="u";break;
                        case 2:ret+="v";break;
                        case 3:ret+="w";break;
                        case 4:ret+="x";break;
                        case 5:ret+="y";break;
                        case 6:ret+="z";break;
                    }
                }
                i+=2;
            }
            else{
                switch(s[i]-48)
                {
                    case 1:ret+="a";break;
                    case 2:ret+="b";break;
                    case 3:ret+="c";break;
                    case 4:ret+="d";break;
                    case 5:ret+="e";break;
                    case 6:ret+="f";break;
                    case 7:ret+="g";break;
                    case 8:ret+="h";break;
                    case 9:ret+="i";break;
                }
                i+=1;
            }
        }
        return ret;
    }
};
```
## 分析总结
答案比较繁琐，主要是解决数字到字母映射的问题，值得学习的地方是不用逆序转化，增加两个判断条件。一开始我没有想明白，为了回避判断（i+2）是否为“#”的时候字符串索引越界。    
现在修改一下自己的答案。

```
class Solution {
public:
    string freqAlphabets(string s) {
        string res="";
        if(s.empty())  return "";
        for(int i=0;i<s.size();i++)
        {
            if(i+2<s.size()&&s[i+2]=='#')
            {
                res+=(s[i]-'0')*10+(s[i+1]-'1')+'a';
                i+=2;
            }
            else
            {
                res+=s[i]-'1'+'a';
            }
        }
        return res;
    }
};
```
