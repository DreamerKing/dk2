---
title: let -- Shell
date: 2016-01-13 00:38:15
tags:
---
### 功能
Shell中执行表达式运算的工具，可以执行常见的运算，还可以执行方幂运算`**`。
**注意**:在let可做用的范围内不需要加`$`来表示变量，其次let可以用来解析字符串并执行运算。
另外let执行计算时，如果计算结果为非0时返回状态值为0;否则返回状态值为1。  
```sh
        let a=23 b=12 c=a+b  
        echo  $a  $b  $c   
```

执行结果：23 12 35   

```sh
        b=5  
        let "t = ((a = 5 + 3, b = b - 1, c = 15 - 4))"  
        echo  $t  $a  $b  $c  
```
执行结果：11  8  4  11  

### 比较区别,加深理解  

不使用let直接执行
```sh
        t=32  
        t=$t+4  
        echo $t  
```
执行结果:32+4  
使用let执行
```sh
        t=32   
        let t=$t+4  
        echo $t   
```
执行结果:36   
**结论：**在Shell中，变量是无类型的。如果变量的值都是数字，则视为数值；如果含有字符，则视为字符串。





