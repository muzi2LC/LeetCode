## 第一次  
```
class Solution {
public:
    string reverseStr(string s, int k) {

        int a=s.size()%(2*k);
        int b=s.size()/(2*k);
        int i=0,j=0;
        while(j<b)
        {
            while(i-(k>>1)<0)  
            {
                swap(s[i+j*2*k],s[k-1-i+j*2*k]);
                i++;
            }
            i=0;
            j++;
        }
        i=0;
        if(a>k)
        {
            while(i-(k>>1)<0)
            {
                swap(s[i+2*k*b],s[k-1-i+2*k*b]);
                i++;
            }
        }
        else
        {
            while(i<(a>>1))
            {
                swap(s[i+2*k*b],s[a-1-i+2*k*b]);
                i++;
            }
        }

        return s;
    }
};
```

## 答案
```
class Solution {
public:
    string reverseStr(string s, int k) {

        for(int start=0;start<s.size();start+=2*k)//将字符串以2*k分成小段，每段里面前k个进行反转
        {
            int i=start,j=i+k-1;
            if(j>(s.size()-1))//如果字符数小于k,则只反转size个
                j=s.size()-1;

            while(i<j)
                swap(s[i++],s[j--]);
        }
        return s;
    }
};
```
## 分析  
思路没问题，主要是写代码的方式有待提高。
