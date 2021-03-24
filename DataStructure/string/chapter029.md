## 第一次  
```
class Solution {
public:
    string toGoatLatin(string S) {
        string res="",str="";
        int num=1;
        for(int i=0;i<S.size();i++)
        {
            str+=S[i];
            if(i!=S.size()-1&&S[i+1]==' ')
            {
                i++;
                Change(str);
                res+=str;
                res+=string(num,'a')+" ";
                num++;
                str="";
            }
        }
        Change(str);
        res+=str;
        res+=string(num,'a');
        return res;

    }
    void Change(string &str)
    {
        if(str[0]=='a'||str[0]=='e'||str[0]=='i'||str[0]=='o'||str[0]=='u'||str[0]=='A'||str[0]=='E'||str[0]=='I'||str[0]=='O'||str[0]=='U')
     {
                    str+="ma";
                }
                else
                {
                    str=str.substr(1)+str[0];
                    str+="ma";
                }
    }
};
```
