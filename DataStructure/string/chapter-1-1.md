第一次：    
```
class Solution {
public:
    string defangIPaddr(string address) {
        string out="";
        for(int i=0;i<address.size();i++)
        {
            if(address.at(i)=='.')
                out+="[.]";
            else
                out+=address[i];
        }
        return out;
    }
};
```

查看题解：
作者：[OrangeMan]<https://leetcode-cn.com/problems/defanging-an-ip-address/solution/cshuang-bai-by-orange-32/>
方法一：
class Solution {
public:
    string defangIPaddr(string address) {
for (int i = 0; i < address.length(); i ++) 
            if (address[i] == '.') address.replace(i,1,"[.]"), i += 2;
        return address;
    }
};
方法二：
```
class Solution {
public:
    string defangIPaddr(string address) {
        string res;
        for (char c : address) 
            if (c == '.') res += "[.]";
            else res += c;
        return res;
    }
};
```
总结：本人的程序和作者的方法二类似，在时间上都ok，但由于新建了一个string，占用一部分内存。而作者的方法一，直接在原字符串上操作，这样不占用额外的内存，在时间和空间利用效率上都达到最好

这里需要注意的点：
1.作者在方法一中，if语句中使用逗号，将两句变成一句，虽然看起来很酷，但是对于他人理解不太友好，对程序运行来说也没有提高效率，一般来说，用分号比较好；
2.本人程序中的使用的是string的at函数，实际上也是可以用下标操作符：两个符号的主要区别在于：at函数在索引越界时候，会抛出错误，而下标操作符号不会；

对于replace函数，是在原来字符串的本身上操作，我们可以看到basic_string 中源代码传入的是引用；但是在返回的时候又在内存中创建了一个副本。如下代码所示：
```
#include <iostream>
#include <string>
using namespace std;
int main()
{
	string str("yousilly");
	cout << str << "  "<<&str << endl;
	string str2 = str.replace(2, 1, "yes");
	cout << str<<"  "<< &str<<endl;
	cout << str2<<" "<<&str2<<endl;

}

输出为：
yousilly  010FFD6C
yoyessilly  010FFD6C
yoyessilly 010FFD48
请按任意键继续. . .
```

