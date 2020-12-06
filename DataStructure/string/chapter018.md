### 初次提交
```
class Solution {
public:
int isPrefixOfWord(string sentence, string searchWord) {
	vector<string> vstr;
	string str="";
	for (int i = 0; i<sentence.size(); i++)
	{
		
		if (sentence[i] != ' ')
		{
			str += sentence[i];
		}
		else 
		{
			vstr.push_back(str);
			str = "";
		}
		if (i == sentence.size() - 1)  vstr.push_back(str);
		
	}
	for (int i = 0; i<vstr.size(); i++)
	{
		if (vstr[i].size()<searchWord.size()) continue;
		int j = 0;
		while (j<searchWord.size())
		{
			if (vstr[i][j] == searchWord[j])   j++;
			else             break;
		}
		if (j == searchWord.size())  
			return i + 1;
	}
	return -1;
}
};
```
### 查看答案
作者：[OrangeMan](https://leetcode-cn.com/problems/check-if-a-word-occurs-as-a-prefix-of-any-word-in-a-sentence/solution/dai-ma-jian-dan-yi-dong-shuang-bai-5xing-by-orange/)  

```
class Solution {
public:
    int isPrefixOfWord(string sentence, string searchWord) {
        istringstream ss(sentence);
        string str;
        for (int i = 1; ss >> str; i ++)
            if (str.find(searchWord) == 0) return i;
        return -1;
    }
};

```
### 分析总结  
用已有的函数接口做和自己想方法做，涉及到两个维度的知识：自己想方法就是造轮子，用别人的方法组合起来就是用别人的轮子。




