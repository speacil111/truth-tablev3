# 真值表计算器终版
  
##v1原版、真值表计算器    
### 1.概述

真值表是离散数学中计算给定命题真值的重要工具，在有n个变元的情况下，共有2^n中组合情况，这使我们在计算复杂公式时变得非常复杂，可不可以使用计算机来完成这个计算呢？

本文使用C++语言来实现真值表的编程。

### 2.基本思路

<font color="red">注</font>：本文符号规则如下：！表示非，&表示且，|表示或，^表示蕴含，~表示双条件 。
 
  无论给出怎么样的命题公式，都可以将其拆分成两个更小的公式来进行某种运算，直到该公式被拆分成一个个单独的命题变量为止，我们使用递归+二叉树的方法来完成

 ### 3.使用方法&注意事项

 1.运行程序(.exe文件可直接运行)，根据提示选择模块1，输入命题公式。

 2.命题只可用a-z，A-Z的单独字母来表示，同时只能使用本文提供的5个逻辑连接词。

 3.尽量保证命题公式的可读性，该程序会对命题合法性进行基本的检查，但不能保证检查出所有错误。 

 4.程序打印真值表。
 
 5.打印完毕后，可选择继续输入命题公式或输入exit退出。
 
### 4.example

输入样例：
    
    请选择功能模块：(输入0退出)
    1
    请输入命题公式：(请尽量多添加括号，尤其是在！联结词前，如(!p))
    (p|q)&r
   
输出样例：

    真值表：
    p  q  r     (p|q)&r
    0  0  0      0
    0  0  1      0
    0  1  0      0
    0  1  1      1
    1  0  0      0
    1  0  1      1
    1  1  0      0
    1  1  1      1
    真值表计算完毕！

##v2、补充功能：根据真值表计算命题公式
使用方法：运行程序，根据提示选择模块2，输入正确的真值表，该程序将会分别从取1行和取0行生成对应的命题公式（若不存在则输出空公式）。   
<font color="red">注</font>：该模块并未添加错误检查功能，请确保真值表格式正确，以及每行的变量赋值正确，最终结果行表头可用字母r代替。

example：

    请选择功能模块：(输入0退出)
    2
    注意：请保证真值表按顺序正确输入！未知结果行表头用r表示，默认从取1行来写
    p q r
    0 0 0
    0 1 1
    1 0 1
    1 1 1
output：

    从取1行生成的命题公式为：(!p&q)|(p&!q)|(p&q)
    从取0行生成的命题公式为：(p|q)

##v3、补充功能：计算主析取范式与主和取范式
使用方法：在真值表打印完毕后根据提示输入'y'来计算主范式。

example（命题公式输入以v1为例）：

    是否要计算主析取、主和取范式？(y/n)
    y
output：
    
    主析取范式：(!p&q&r)|(p&!q&r)|(p&q&r)
    主合取范式：(p|q|r)&(p|q|!r)&(p|!q|r)&(!p|q|r)&(!p|!q|r)

## Reference
 
1.http://blog.csdn.net/patrick_lyle/article/details/63250699

2.Chatgpt 

## Github
https://github.com/speacil111/truth-tablev3