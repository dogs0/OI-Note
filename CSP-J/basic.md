# NOI-CSPJ
//先写一些简单地宏定义(应该没人不会CPP吧)  
```c++
#define ll long long  
#define max(a,b) a>b? a:b  
#define min(a,b) a<b? a:b
```
## 关于计算机  
\-\-|图灵提出的图灵机模型  
\-\-|冯诺依曼架构  
## 关于NOI-CSP
NOI是China National Olympiad in Informatics)  
全国青少年信息奥赛(创建了一种独特的,恶心人的NOI赛制)  
CSP是Certified Software Professional Junior/Senior  
非专业级别软件能力认证,入门级(Junior)和提高级(Senior)  
CCF是China Computer Federation  
中国计算机协会  


## 基础
bit/binary digit 比特位,数据最小单位  
Byte(1Byte=8bits) 字节  
Word(???) 字,n组字节,还tm是计算机基础存储运算单位  

** 简单略过语言了 **  

## g++概要
$ g++ Input.cpp -O0 -o Out.cpp #一般的程序编译规则  
  g++ 输入文件  O0优化 输出  

## C++
switch-case-default  
### 数据大小
知道数据大小Very重要  
(不然容易MLE)  
|名称|大小(sizeof)|范围|
|---|---|---|
|int|4B|2后面9个0|
|ll|8B|9后面18个0|
|float|4B|7位|
|double|8B|15位|
|char|B|不会请退|
|bool|B|是1B!!!|

#### 数据声明
```C++
<类型> 名称;  //一般类型声明
<类型> *名称 = new <类型>;  //一般指针声明
<类型> *名称 = new <类型>[大小];  //一般指针数组声明(可以定义大小但比同等大小的数组大一些
<类型> 名称[大小(const!)];  //一般一维数组声明
```

#### struct和union
struct是一个结构体
大小为所有的成员大小和
union为联合体(共用内存)
大小为最大的成员大小
operator是重载符号用的
不占用空间
语法:
<返回类型> operator <符号> (参数){};

```C++
struct A{  //一个名为A的类型
  int a;  //成员a
  A(){};  //一个特殊的构造函数
  A(int k){};  //有整数参数的构造函数
  int operator + (int m) {return m+a;};
}K,L(1);

union B{
  float k,l;  //成员k,l和a共用内存
  int a;
}M; 
int main(){
  K.a=0;  //赋值
  M.k=1.14;
  if (M.k==M.l) return 0;
  return 1;
}
```
以上程序的返回值为0
### 输入输出
#### cin/cout
~个人感觉不如printf~  
属于iostream  
(精度控制用iomanip)  
示范:  
```C++
#include<iostream>
#include<iomanip>
using namespace std;
int main(){
    setiosflags(ios::fixed);//固定小数位但没卵用
    cout << setprecision(9) << 1.14514191981 << endl; //控制九位小数
    cout << 1.145141919810; //《连坐》
    // 有四舍五入
    return 0;
}
```
输出:  
```
1.14514192
1.14514192
```
#### printf/scanf
先来个格式表:  
|格式|意义|
|---|---|
|d|十进制数|
|u|无符号的d|
|f|实数|
|l|长|
|.|范围限制|

(02.3:如数字不满2字节,则补0,小数超过三字节四舍五入)  
(lf:长实数;ld:ll)  
格式:  
`printf("格式",参数们);`  
`scanf("格式",参数的地址)`  
(必须是地址,不然传了个野指针)  

示范:  
```c++
#inclued<cstdio>
int main(){
    long long a;
    scanf("%lld",&a);
    printf("%lld",a);
    return 0;
}
```
输入出  
```
114514
---
114514
```

#### 常用宏
```c++
#define max(a,b) a\>b? a:b
#define min(a,b) a\<b? a:b
#define abs(a) a\<0? -a:a
#define round(a) a\>=((int)a+0.5) ((int)a+1):((int)a)
#define ceil(a) a>(int)a? (int)a+1:(int)a
#define floor(a) (int)a
```
