
# string 标准库

查阅资料：C++ [string类型](http://www.cplusplus.com/reference/string/string/)

## 要点：
typedef basic_string\<char\> string: string 实际上是根据basic_string模板生成的一个处理char类型的字符串类.  
basic_string类型定义：  
template \< class charT,  class traits = char_traits\<charT\>, class Alloc = allocator\<charT\>  \> class basic_string;  
注意：在模板中class与typename等效

第一个参数charT表示要存储在字符串中单个字符的数据类型      
第二个参数traits表示基本的属性  
第三个参数表示存储的分配器对象的类型  

## 刷题
leetcode刷题  
1.1108. IP 地址无效化       [答案](chapter-1-1.md)  
2.1614. 括号的最大嵌套深度  [答案](chapter-1-2.md)  
3.1370. 上升下降字符串      [答案](chapter-1-3.md)  
4.1436. 旅行终点站          [答案](chapter-1-4.md)






