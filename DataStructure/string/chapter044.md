## 第一次  
```
class Solution {
public:
    string addStrings(string num1, string num2) {
        if(num2.size()<num1.size()) return addStrings(num2,num1);
        int over=0,sum=0,x=0,y=0;
        string res="";
        for(int i=num2.size()-1;i>-1;i--)
        {
            y=num2[i]-'0';
            if(i<num2.size()-num1.size()) x=0;
            else                x=num1[i-num2.size()+num1.size()]-'0';
            sum=x+y+over;
            if(sum>9)  { over=1;sum=sum%10;}
            else        over=0;
            res=char('0'+sum)+res;
        }
        if(over==1)  res='1'+res;
        return res;
    }
};
```
