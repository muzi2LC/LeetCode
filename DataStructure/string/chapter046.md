## 第一次  
```
class Solution {
public:
    string reverseVowels(string s) {
        if(s.empty())   return s;
        int low=0,high=s.size()-1;
        while(true)
        {
            while(!isVowel(s[low])&&low<high)  low++;
            while(!isVowel(s[high])&&low<high) high--;
            if(low>=high)  break;
            else          
            {
                swap(s[low],s[high]);   
                low++;
                high--;
            }
        }
        return s;
    }
    bool isVowel(char ch)
    {
        if(ch=='a'||ch=='A')  return true;
        if(ch=='e'||ch=='E')  return true;
        if(ch=='i'||ch=='I')  return true;
        if(ch=='o'||ch=='O')  return true;
        if(ch=='u'||ch=='U')  return true;
        return false;
    }
};
```
