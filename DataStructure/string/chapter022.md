## 第一次  
```
class Solution {
public:
    string interpret(string command) {
        string str="";
        if(command.empty())  return "";
        for(int i=0;i<command.size();i++)
        {
            if(i<command.size()-3)
            {
                if(command[i]=='G')   str+="G";
                else{
                    if(command[i+1]==')')
                    {
                        str+="o";
                        i++;
                    }
                    else{
                        str+="al";
                        i+=3;
                    }
                }
            }
            else
            {
                if(command[i]=='G')  str+="G";
                else{
                    str+="o";i++;
                }
            }
        }
        return str;
    }
};
```
##  答案
```
class Solution {
public:
    string interpret(string command) {
        for(int i = 0; i < command.size(); i++)
        {
            if(command[i] == '(' && command[i+1] == ')')
            {
                command = command.replace(i, 2, "o");
            }
            else if(command[i] == '(' && command[i+1] == 'a')
            {
                command = command.replace(i, 4, "al");
            }
        }
    return command;
    }
};
```

