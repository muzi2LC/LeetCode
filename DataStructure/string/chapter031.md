## 第一次  
```
class Solution {
public:
    string thousandSeparator(int n) {
        if(n==0)  return "0";
        int k=0,count=0;
        string str="";
        while(n!=0)
        {
            count++;
             k=n%10;
            n=n/10;
            str=char('0'+k)+str;
            if(count==3&&n!=0)
            {
                count=0;
                str='.'+str;
            }
        }
        return str;
    }

};
```
