# 关于cstring
## 前置基础
```c++
char *str0 = new char[<size>];  //一个指针字符数组
char str1[<size>];              //一个字符数组
//'\0'是字符数组的结束标识
//函数返回不能用数组，能用指针
```

## cstring的那些函数

(虽然但是,尽量自己造)  
(以下未说明的参数均为char*,char[]类型)

|函数名|功能|
|---|---|
|strcpy(a,b)|拷贝b2a|
|strcat(a,b)|拼接b2a的末尾|
|strlen(a)|'\0'前的字符个数|
|strcmp(a,b)|如a==b,返回0,否则设第一个不同的字符为 $a_i$ , $b_i$ 返回 $a_i - b_i$ |
|strchr(a,char x)|如果 $ b \in a $ ,则返回a中b的第一个位置,否则为NULL|
|strstr(a,b)|同上，但是char*|

