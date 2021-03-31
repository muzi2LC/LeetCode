## 第一次  
```
class Solution {
public:
    int numDifferentIntegers(string word) {

        string subStr="";
        vector<string> vec;
        bool flag=false;
        for(int i=0;i<word.size();i++)
        {
            if(word[i]>='0'&&word[i]<='9')
            {
                if(!(subStr.empty()&&word[i]=='0'))  subStr+=word[i];
                flag=true;
                if(i==word.size()-1)
                {
                    if(canGet(vec,subStr))   vec.push_back(subStr);
                }
            }
            else
            {
                if(flag&&canGet(vec,subStr))  vec.push_back(subStr);
                flag=false;
                subStr="";
            }  
        }
        return vec.size();


    }
    bool canGet(const vector<string> &vec,string str)
    {
        bool flag=true;
        for(int i=0;i<vec.size();i++)
        {
            if(vec[i]==str)  flag=false;
        }
        return flag;
    }
};

```
