## 第一次  
```
class Solution {
public:
    string addBinary(string a, string b) {
        int isOver=0;
        int i=a.size()-1,j=b.size()-1;
        string res="";
        int num1,num2,num;
        while(true)
        {
            if(i==-1&&j==-1)
            {
                if(isOver==1)  res="1"+res;
                break;
            }
            if(i==-1)  num1=0;
            else      num1=a[i]-'0';
            if(j==-1)  num2=0;
            else      num2=b[j]-'0';
            num=num1+num2+isOver;
            switch(num){
                case 0:    res="0"+res;  isOver=0; break;
                case 1:    res="1"+res;  isOver=0; break;
                case 2:    res="0"+res;  isOver=1; break;
                case 3:    res="1"+res;  isOver=1; break;
            }
            if(i!=-1)   i--;
            if(j!=-1)   j--;
        }
        return res;
    }
};

```
