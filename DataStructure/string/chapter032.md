## 第一次  
```
class Solution {
public:
    string gcdOfStrings(string str1, string str2) {
        if(str1.size()==0||str2.size()==0)  return "";
        string str3=findMinRepeat(str2);
        string str4=findMinRepeat(str1);
        if(str3!=str4)  return "";
         int num=findMaxNum(str1.size()/str3.size(),str2.size()/str3.size());
         while(--num)
         {
             str3+=str4;
         }
        return str3;
    }
    string findMinRepeat(string str)
    {
        string str1="";
        int k=0;
        for(int i=0;i<str.size();i++)
        {
            k=str.size()%(i+1);
            if(k==0)   
            {
                for(int j=0;j<str.size()/(i+1);j++) str1+=str.substr(0,i+1);
                if(str1==str)   return str.substr(0,i+1);
                else            str1="";
            }
 
        }
        return str;
    }
    int findMaxNum(int i,int j)
    {
        int k=0;
        if(j>i)  swap(i,j);
        while(true)
        {
             k=i%j;
            if(k==0)  return j;
            else    
            {
                i=j;
                j=k;
            } 
        }
    }
};
```
## 答案 
```


class Solution {
public:
    string gcdOfStrings(string str1, string str2) {
        if(str1+str2!=str2+str1) return "";
        return str1.substr(0, gcd(str1.length(), str2.length()));
    }

    inline int gcd(int a,int b){
        return b==0?a:gcd(b, a%b);
    }
};
```
