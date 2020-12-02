
### 初次提交
```
class Solution {
public:
    int balancedStringSplit(string s) {
        	int i = 1;
	        int k = 0;
	        char ch1 = s[0];
	        for (size_t j=1;j<s.size();j++){
          if (ch1 == 'L'){
          if (s[j] == 'L')
              i++；
          else
              i--；
          }
          else
          {
          if (s[j] == 'R')
             i++;
          else
            i--；
         }
         if (i == 0)
            k++；
         }
         return k;
    }
};
```
### 优化一下：
```
class Solution {
public:
    int balancedStringSplit(string s) {
        	  int res  = 0;
            int count= 0;
            for (char ch:s)
            {
                if(ch=='L')   count++;
                else          count--;
                if(count==0)  res++;
            }
            return res;
    }
};
```
