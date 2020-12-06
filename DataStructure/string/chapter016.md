### 初次提交
```
class Solution {
public:
int numUniqueEmails(vector<string>& emails)
{
	unordered_set<string> res;
	for (string str : emails)
	{
		string s="";
		for (int k = 0; k<str.find('@'); k++)
		{
			if (str[k] != '.')
				s += str[k];
		}
        s=s.substr(0,s.find('+'));
        s+=str.substr(str.find('@'));
		res.insert(s);
	}
	return res.size();
}
};
```
### 查看答案
```
class Solution {
public:
    string tipMailAdress(string& s) {
		 int n = s.length();
		 string temp = "";
		 bool isAt = false;
		 for (int i = 0; i < n; i++)
		 {
			 if (s[i] == '@') { isAt = true; temp += s[i]; continue; }
			 if (!isAt) {
				 if (s[i] == '.') continue;
				 if (s[i] == '+') {
					 while (i < n && s[i] != '@')
						 i++;
                     i--;
					 continue;
				 }
				 temp += s[i];
			 }
			 else {
				 temp += s[i];
			 }
		 }
         cout << temp << " ";
         return temp;
	 }
    int numUniqueEmails(vector<string>& emails) {
        set<string> s;
		 int n = emails.size();
		 for (int i = 0; i < n; i++)
		 {
			 s.insert(tipMailAdress(emails[i]));
		 }
		 return s.size();
    }
};
```
