## 第一次  
```
class Solution {
public:
    string reverseOnlyLetters(string S) {
        for(int i=0,j=S.size()-1;i<j;)
        {
            if(isLetter(S[i])&&isLetter(S[j])) 
            {
                swap(S[i],S[j]);
                i++;
                j--;
            }
            else
            {
                if(!isLetter(S[i]))  i++;
                if(!isLetter(S[j]))  j--;
             }
        }
        return S;

    }
    bool isLetter(char ch)
    {   
        if((ch-'a'>-1&&ch-'z'<1)||(ch-'A'>-1&&ch-'Z'<1))  return true;
        return false;
    }
};

```
