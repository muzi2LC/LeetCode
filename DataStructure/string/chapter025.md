## 第一次  
```
class Solution {
public:
    bool halvesAreAlike(string s) {
        if(s.size()%2==1)  return false;
        int charMap[58]={0};
        int num=0;
        string str="aeiouAEIOU";
        for(char ch:str)
        {
            charMap[ch-'A']=1;
        }
        for(int i=0;i<(s.size()>>1);i++)
        {
            if(charMap[s[i]-'A']==1) num++;
            if(charMap[s[s.size()-i-1]-'A']==1)  num--;
        }
        return num==0;
    }
};
```

## 答案
```
class Solution {
public:
    bool halvesAreAlike(string s) {
/*           bool vowel(char m){
            if(m=='a'||m=='e'||m=='i'||m=='o'||m=='u'||m=='A'||m=='E'||m=='I'||m=='O'||m=='U')
                return true;
            else
                return false;
        }
*/
        int numl=0,numr=0;
        for(int i=0;i<s.size()/2;i++){
            int j=s.size()-1-i;
            numl+=(s[i]=='a'||s[i]=='e'||s[i]=='i'||s[i]=='o'||s[i]=='u'||s[i]=='A'||s[i]=='E'||s[i]=='I'||s[i]=='O'||s[i]=='U');
            numr+=(s[j]=='a'||s[j]=='e'||s[j]=='i'||s[j]=='o'||s[j]=='u'||s[j]=='A'||s[j]=='E'||s[j]=='I'||s[j]=='O'||s[j]=='U');
        }
        return numl==numr;
    }
};
```
## 分析  
这道题的核心思想是判断是否为元音字母，有多种方法
