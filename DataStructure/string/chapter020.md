## 自己尝试：  
```
class Solution {
public:
    vector<int> numSmallerByFrequency(vector<string>& queries, vector<string>& words) {
        vector<int> vec;
        for(int i=0;i<queries.size();i++)
        {
            int cont=0;
            for(int j=0;j<words.size();j++)
            {
                if(findStrMin(queries[i])<findStrMin(words[j]))
                   cont++;
            }
            vec.push_back(cont);
        }
        return vec;
    }
    int findStrMin(string str)
    {
        int cont=1;
        char ch=str[0];
        for(int i=1;i<str.size();i++ )
        {
            if(ch>str[i])
            {
                ch=str[i];
                cont=1;
            }
            else if(ch==str[i])
            {
                cont++;
            }
        }
        return cont;
    }
};
```
超出时间限制无法提交。发现words中重复搜索了很多次。修改一下：
##  修改第一版
```
class Solution {
public:
    vector<int> numSmallerByFrequency(vector<string>& queries, vector<string>& words) {
        vector<int> vec;
        vector<int> wordsVec;
        for(int i=0;i<words.size();i++)
        {
            wordsVec.push_back(findStrMin(words[i]));
        }
        for(int i=0;i<queries.size();i++)
        {
            int cont=0;
            for(int j=0;j<words.size();j++)
            {
                if(findStrMin(queries[i])<wordsVec[j])
                   cont++;
            }
            vec.push_back(cont);
        }
        return vec;
    }
    int findStrMin(string str)
    {
        int cont=1;
        char ch=str[0];
        for(int i=1;i<str.size();i++ )
        {
            if(ch>str[i])
            {
                ch=str[i];
                cont=1;
            }
            else if(ch==str[i])
            {
                cont++;
            }
        }
        return cont;
    }
};
```
时间上仍旧不太理想   
## 查看答案  
```
class Solution {
public:
    int getFrequency(string& s) {
		 array<int, 26> arr;
		 arr.fill(0);
		 int n = s.length();
		 for (int i = 0; i < n; i++)
		 {
			 arr[(int)(s[i] - 97)]++;
		 }
		 int f = 0;
		 for (int i = 0; i < 26; i++)
		 {
			 if (arr[i] != 0) { f = arr[i]; break; }
		 }
		 return f;
	 }
	 vector<int> numSmallerByFrequency(vector<string>& queries, vector<string>& words) {
		 int n = queries.size(), m = words.size();
		 array<int, 11> wordFrequency, wordFrequencyCount;
		 wordFrequency.fill(0);
		 for (int i = 0; i < m; i++)
		 {
			 int index = getFrequency(words[i]);
			 wordFrequency[index]++;
		 }
		 int total = 0;
		 for (int i = 0; i < 11; i++)
		 {
			 total += wordFrequency[i];
			 wordFrequencyCount[i] = total;
		 }
		 vector<int> v;
		 for (int i = 0; i < n; i++)
		 {
			 int queryFrequency = getFrequency(queries[i]);
			v.push_back(wordFrequencyCount[10] - wordFrequencyCount[queryFrequency]);
		 }
		 return v;
	 }
};
```

##  根据答案修改自己的代码
```
class Solution {
public:
    vector<int> numSmallerByFrequency(vector<string>& queries, vector<string>& words) {
        vector<int> vec;
        int arr[11]={0};
        int arr2[11]={0};
        for(int i=0;i<words.size();i++)
        {
            int index=findStrMin(words[i]);
            arr[index]++;
        }
        int total=0;
        for(int i=0;i<11;i++)
        {
            total+=arr[i];
            arr2[i]=total;
         } 
        for(int i=0;i<queries.size();i++)
        {
            vec.push_back(arr2[10]-arr2[findStrMin(queries[i])]);
        }
        return vec;
    }
    int findStrMin(string str)
    {
        int cont=1;
        char ch=str[0];
        for(int i=1;i<str.size();i++ )
        {
            if(ch>str[i])
            {
                ch=str[i];
                cont=1;
            }
            else if(ch==str[i])
            {
                cont++;
            }
        }
        return cont;
    }
};
```

##  总结分析   
这里将每个最小值利用数字记录下来，就不需要再次遍历；



