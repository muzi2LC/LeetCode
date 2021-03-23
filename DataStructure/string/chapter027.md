## 第一次  
```
class Solution {
public:
    bool areAlmostEqual(string s1, string s2) {
        if(s1==s2)  return true;
        if(s1.size()!=s2.size())  return false;
        int i=0,j=s1.size()-1;
        while(i<s1.size())
        {
             if(s1[i]!=s2[i])  break;
             i++;
        }
        while(j>0)
        {
            if(s1[j]!=s2[j])  break;
            j--;
        }
        if(j!=-1&&i!=s1.size())   swap(s1[i],s1[j]);   
        return s1==s2;       
    }
};
```
## 答案 
```
class Solution {
public:
    bool areAlmostEqual(string s1, string s2) {
int num=0;
bool s=false;
int a[3];
for(int i=0;i<s1.size();i++)
{
   if(s1[i]!=s2[i])
    { 
    a[num]=i;
      num++;
     if (num==3)
    {
        break;
    }
    }
     
}
if(num==2&&s1[a[0]]==s2[a[1]]&&s1[a[1]]==s2[a[0]])
{
s=true;
}
else if(num==0)
s=true;
return s;
    }
};
```
## 分析  
答案的好处时只进行一次遍历。
