# **本文为CPL笔记**
- [**本文为CPL笔记**](#本文为cpl笔记)
  - [插件](#插件)
  - [cpl](#cpl)
    - [第一节课](#第一节课)
      - [代码示例](#代码示例)
      - [cmake](#cmake)
    - [第二节课](#第二节课)
    - [第三节课](#第三节课)
    - [第四节课](#第四节课)
    - [第五节课](#第五节课)
    - [第六节课](#第六节课)
    - [第六节课](#第六节课-1)
    - [第七节课](#第七节课)
    - [第八节课](#第八节课)
    - [第九节课](#第九节课)
    - [第十节课](#第十节课)
    - [第十一节课](#第十一节课)
      - [能作为参数](#能作为参数)
      - [函数能被赋值给变量](#函数能被赋值给变量)
      - [函数作为返回值:返回一个函数指针](#函数作为返回值返回一个函数指针)
    - [第十二节课](#第十二节课)
      - [结构体](#结构体)
      - [枚举类型](#枚举类型)
    - [第十三节课](#第十三节课)
      - [什么是链表(数据类型/数据结构)](#什么是链表数据类型数据结构)
      - [链表的实现](#链表的实现)

## 插件
1. caps2ctrl
2. tabnine

## cpl

### 第一节课
#### 代码示例
**示例一 [hello world]()"D:\Freshman\cpl\example_in_class\hello_world\hello.c"**

==语言只是一种手段一种工具==
**先用自然语言编程**
*不成文规定：一行代码在78到80字符*
[手册](https://en.cppreference.com/w/c)

**示例二 [guessing number]()"D:\Freshman\cpl\example_in_class\guessing_nimber\main.c"**

#### cmake
```
cmake_minimum_required(VERSION 3.26) //声明最低版本
project(guessing_nimber C) //项目名称

set(CMAKE_C_STANDARD 17) //定义c标准为c17

add_executable(guessing_nimber main.c) //生成可执行文件(等价于gcc guessing_nimber.c -o main.c)

```

一个项目下可以创建多个c源代码文件
需要在add_executable后手动加入



### 第二节课
**variables,types,I/O**
Program = input + data + operations + output

1. **variables 变量**
2. **data types 数据类型**
3. **operations**

radius refers to a location(&radius)in memory
地址
& 取地址运算符
==变量的值和地址的值是两回事==

**示例一**
计算圆形的周长和面积

- 尽量不要出现magic_number(定义常数)

- 重构可一次改变所有变量的名称

- 标识符不要以 "_" 开头(保留字符)
- 变量要有意义,尽量用英文

**示例二**
计算球的表面积和体积

**示例三**
为罗大佑创建admin

- 解决编译器找不到 math.h 问题
```
target_link_libraries(admin m)
```

- alt + shift + enter 自动补充头文件

- %%:输出一个%

**Undefined Behavior**
1. printf函数中前后不对应


**示例四**
- %s: 前导空白符忽略,直到有字符,并结束于下一个空白符之前 ==输入字符串==
- %c: 不会忽略前导空白符
- scanf函数中的"space":用来消耗用户输入的空白符 ==一般情况慎用空格==
- %d: 忽略前导空白符,直到寻找到一个整数并识别
- %9s: 限制只能读入9个字符
- scanf中的普通字符: 匹配并寻找其自身

**Do Not use scanf**

### 第三节课
**if-for-array**
==Overview==
1. if statement
2. for statement
3. logical expressions
4. array

**if statement**
- 代码风格
空格,花括号
- min = a < b ? a : b; 三元运算符
```
if (a < b){
  min = a;
}
else {
  min = b;
}
```
*少用 ==不利于代码可读性==*
**不要表现得太聪明**
- 小技巧:先把if else的框架写好
- 小技巧:若else嵌套得很深,写一个注释方便检查
- if else可以嵌套

**示例一**
- int leap = 0; //定义一个指示变量(bool / flag) 0/1
- 在if语句中判断相等为 ==
- 遇到两个分支,其中一个比较简单,先写简单分支
- 避免箭头代码(头重脚轻)
- 代码格式化
- 级联式if语句
```
if{

}
else if{

}
else{

}
```

- 优先级容易忘,直接加括号解决
- else 不是必须的
- 合理运用逻辑表达式的返回值简化代码
==注意可读性==
- 短路求值
```
if ((year % 4 ==0 && year % 100 != 0) || 
(year % 400 == 0))
```

**示例二**
- 若重复做一个动作就要考虑循环
- 一个循环具有的两要素
1. 循环的内容
2. 循环结束的条件
- 数组下标从0开始
- 访问数组中的元素也是按照下标访问
- for循环
```
for(初始化;条件(循环还要继续下去的条件);用作迭代的表达式){
  循环体
  }
```
- for( ; ; )**分号不能省略**
1. 初始化:先执行,且只被执行一次
2. 条件:每次循环前执行,判断条件是否成立
3. 若条件成立:进入循环体
4. 循环体做完:进入迭代表达式
- 判断条件(回到2.)
5. 若条件不成立:跳出循环,继续进行下面的事情

- 理解for循环语意
==多练多看==
- numbers[i] 当作变量使用
- 初始化只作用在for循环内部(作用域)(c99)
好处:节省变量名

### 第四节课
**for-a-while**
*clion中调试for语句:见[b站视频](https://www.bilibili.com/list/watchlater?oid=789412272&bvid=BV1AC4y1d7KX&spm_id_from=333.1007.top_right_bar_window_view_later.content.click)*

- wolframealpha

**示例二**
- break:跳出一层循环
- 计算机中输入和输出是最慢的
- c99之后在宏中定义了bool变量
```
#include <stdbool.h>
```
- 允许你bool变量的值非1/0
==不要这样用==

**示例三 二分查找**

[理解二分查找的边界条件](https://blog.csdn.net/qq_45978890/article/details/116094046)
- 二分法分割已排序的数组
- 时间复杂度从线性到lg(n)
```
while (low <= high) {
        int mid = (low + high) / 2;

        if (key > dict[mid]) {
            low = mid + 1;
        } else if (key < dict[mid]) {
            high = mid - 1;
        } else {
            index = mid;
            //break;
            high = mid - 1;//找最左边的k
        }
    }
```
==熟读并背诵==

==边界条件==
二分法最重要的两个点
1. while循环中right和left的关系 left<= right / left< right
2. 迭代过程中middle和right的关系 right=middl-1 / right=middle

1. 左闭右闭
```
while (low <= high) {
        int mid = (low + high) / 2;

        if (key > dict[mid]) {
            low = mid + 1;
        } else if (key < dict[mid]) {
            high = mid - 1;
        } else {
            index = mid;
            //break;
            high = mid - 1;//找最左边的k
        }
    }
```
2. 左闭右开
```
while (low < high) {
        int mid = (low + high) / 2;

        if (key > dict[mid]) {
            low = mid + 1;
        } else if (key < dict[mid]) {
            high = mid;
        } else {
            index = mid;
            //break;
            high = mid - 1;//找最左边的k
        }
    }
```

**示例四**
- do while:先做一次循环再判断条件是否成立
==while 后面有一个分号==
*一般比较少用*


**示例五 排序算法**
选择排序
1. 从数组中选出最小值（selection）
2. 和数组的第一个位置交换
3. 剩下的数组再找出最小值
4. 再和剩下的数组的第一个位置交换
5. 迭代

- scanf的返回值
1. input failure:EOF (end of file,通常为-1)
数据流已经坏了读不出数据了
2. number of matched items:返回之前成功匹配多少个数据(肯定大于等于0)
数据类型不匹配
- 换行将缓冲区的内容发送给scanf
- linux系统下 ctrl+d 强制将缓冲区内容发送给scanf
若缓冲区为空,则会发送EOF信号 
- 输入重定向:不再从控制台(标准输入设备)由用户输入
可以从文件输入
- 输出重定向:不再从控制台(标准输出设备)输出

### 第五节课
**多维数组**

**示例一**
生命游戏
- 二维数组的初始化
1. 按行初始化,每一行当作一个一维数组
2. 按下标初始化
3. 当作一维数组初始化,先填第一行再填第二行(本质上是一维数组)
- Sleep(1000)
<synchapi.h>
- system("cls")
<stdlib.h>

**示例二**
merge
- 当出现一个问题,他的规模变了但本质不变
==考虑循环==
- 根据这个子任务可以完成数组的排序
==合并排序==

### 第六节课
**函数**

***overview***
- 函数定义
- 函数申明
- 数组作为函数参数
- pass by value 传值

---
- 函数:
1. 实现封装
将实现细节封装进函数中(main函数中不关心的)
从而降低认知复杂度
1. 代码复用
- 定义一个函数
1. 返回值的类型
2. 函数名
3. 函数接受的参数(参数类型+参数名)
形式参数,同样为块作用域
1. 函数体
```
bool IsLeapYear (int year){ //year:形式参数(占位符)
    bool leap = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    return leap;
}
```
***caller 调用者***
***callee 被调用者***
- 函数声明
在写函数体之前显式地写出函数的返回值
将其具体实现(定义)写在后面
- 局部变量
在函数体内定义的变量
- 块作用域
局部变量的块作用域
- return 语句
- 数组作为函数参数
不用给定数组大小(==形参是这个数组的第一个元素的地址==)
但需要再给定一个表示数组大小的参数(防止数组越界)
数组前加const 表示数组内元素不可被修改
- 全局变量
文件作用域:从定义开始到整个文件结束
==基本原则:作用域越小越安全(尽量不要用全局变量)==
- 每当定义一个变量时要给他一个有意义的初始值
- 字符串作为参数时不用给定表示数组大小的参数
可以用strlen给出
- pass by value
传值:由实参传给形参的只是一份拷贝内容,形参的改变并不会影响实参
若传的为地址,则形参可以跟据地址改变实参
- 二维数组作为形参
==数组的首地址+数组的类型 即可得到数组中任意元素的地址==
第一个中括号空着
第二个中括号不能空
首地址+ 1 * (size of a row) *[col *(size of int)] + 2 * (size of int)=address of a[1][2]

### 第六节课
**递归(递归函数)**==最困难的部分==
 A function that calls itself
 甚至可以在main函数中调用main函数
一种思考方式 
1. **Thinking like a Computer Scientist**
Solving a task by the first solving its smaller subtasks.
先向下推导找子问题直到找到一个base case
再由base case的解不断向上传播直到原问题求出解
主要是三个问题
- 子任务是什么 *****
- 由子任务的解怎么得到原始任务的解 ***
- 最小任务(base case)是什么 *

***It will be a looooong way to go to master RECURSION!!!***

2. **Thinking like a Computer**
非递归函数是怎么调用的?
- 调用时会分配栈帧(stack frame),控制权给被调用的函数
知道变量的名称和类型但不知道具体值
- 调用结束后数据返回给调用者,控制权归还给调用者
*局部变量/全局变量 (作用域角度)
自动变量/静态变量 (生命周期角度)*
自动变量:会随着栈帧的消失而消失
静态变量:只有当程序结束时才会消失
递归函数是怎么调用的?
- 每次递归调用函数本身都会新创建一个栈帧
- 调用结束后返回给调用者,控制权归还给调用者调用函数的地方

```
int Min(const int nums[], int len) {
    if (len == 1) {
        return nums[0]; //最小问题的解
    }

    int partial_min = Min(nums, len - 1);//子问题

    return partial_min < nums[len - 1] ? partial_min : nums[len - 1];//由子问题得到原始问题
}
```
得到数组的长度
```
sizeof numbers / sizeof(int);
sizeof numbers / sizeof numbers[0];
```

### 第七节课

合并排序==递归版==
子问题:merge sort(n/2) 分为两个子问题
由子问题解决原始问题:merge 两个子问题
注意递归函数的参数:***要能区分每个子问题***,单纯的数组长度不可以表示

tips:文档注释
```
/**
```

数据类型
int char double bool []

整型类型
- short (int)
- int 
- long (int)
- long long (int)
***long int 不一定比int 大 直接用long long int***

unsigned:无符号
输出用 %zu
==慎用==

typedef:类型定义
```
typedef unsigned long long int size_t;

typedef long long time_t;
```

char不会默认有无符号

有符号整数的溢出:UB
无符号整数没有溢出:回绕 
UINT_MAX+1=0

算术表达式\逻辑表达式 (先做整型提升)
函数调用
==隐式类型转换(危险)==

显式类型转换
(type) expression
```
pi - (int) pi;
```

浮点类型
1. float
```
float pi 3.14F
```

比较浮点数的大小不能直接看是否相等

==浮点数的运算非常难==

### 第八节课
Pointers And Arrays
==指针==
五句话教你学会指针
5=3(pointers)+2(arrays)

1. 变量的三个属性:类型,值,地址
&:取地址符
%p:输出地址 (p:point指针就是地址地址就是指针)
2. 变量既可以作为左值也可以作为右值使用
左值: ```radius=200;``` 相当于变量所在的空间(地址)
右值: ```double circumference = 2 * PI * radius;```相当于变量的值
3. ==指针就是一个变量,这个变量存的值是另外一个变量的地址==
```int *ptr_radius1 = &radius1;```
int *:指向int的指针变量(类型名)
*:解引用 间接运算符(一元运算符)
```*ptr_radius1```和```radius1```可以互换
noticing:当多个指针变量指向同一个变量时,改变其中一个指针变量都会改变这个变量

```
void Swap(int *left, int *right) {
    int temp = *left; 
    *left = *right;
    *right = temp;
}
```
函数调用时:
```Swap(&numbers[i],&numbers[j]);```
传值:由实参传给形参的只是一份拷贝内容,形参的改变并不会影响实参
若传的为地址,则形参可以跟据地址改变实参
left = &numbers[i]
right = &numbers[j]

```pv = &pv```等号左右的类型不匹配 int * 和int **(双重指针)


4. ==在表达式中==,数组名(永远)就是数组的首元素的地址
- 表达式:变量,常量,运算符
():函数调用运算符

```SelectionSort(&numbers[0], LEN);```和```SelectionSort(numbers, LEN);```相同

语法糖现象:
- int arr[] <=>int *arr
- arr[i] <=> *(arr + i) <=> *(i + arr) <=> i[arr]

指针的算术运算
```arr + i, arr - i```
指针和整数的运算只能用于数组
```p - q```

&arr[i] <=> &(*(arr+i)) <=> arr+i

5. 但是数组名不是一个指针变量
不能修改这个数组名使他指向另一个变量
NOT ALLOWED```arr = arr + 1```

==动态内存管理==
void *malloc(size_t(无符号整数) Size); stdlib中
(void *: 因为不知道要填什么类型数据)
```int *numbers = malloc(len * sizeof(int));```<=>```int *numbers = malloc(len * sizeof(*numbers));```
内存分配
```
if (numbers == NULL){ //NULL:空指针#define NULL ((void *)0)
  return 0;
}
```
判断内存分配是否成功

分配到的内存空间不指定用作什么

malloc分配的空间不在栈上面而在堆上面,main函数结束时栈帧消失没有人能访问堆上分配的内存了:内存泄漏
***malloc申请的空间在不需使用后要显式地释放***
```free (numbers);```
void free (void *ptr);
- 不能多次free
- free之后不能再访问
- 不能free栈上的空间

int * const :指针变量不能变(不能指向其他变量)

### 第九节课
指针和字符串
如何在c语言中用指针去操作字符串(以\0 结束的字符数组)
```
char *ptr_msg = "Hello World!";
```
实际是一个字符数组

通过指针修改了不该修改的区域导致 段错误
*SIG: signal; SEGV: segmentation violation*

```const char *str```保护字符串不被修改(不是保护指针变量)

### 第十节课
双重指针
1. char *musicians[LEN]
是个长为LEN的数组,数组中的每个元素是char *(指针)
==指向字符串的首地址==
指针存放在栈帧当中,而指针指向的内容存放在一块==只读==区域

**eg:选择排序**
```
void Print(const char *arr[], int len) {
    printf("\n");
    for (int i = 0; i < len; i++) {
        printf("%s\n", arr[i]); //arr[i]就是一个指针(字符串的首地址)
    }
    printf("\n");
}
```

```
int GetMinIndex(const char *arr[], int begin, int end) {
    const char *min = arr[begin];
    int min_index = begin;

    for (int i = begin + 1; i < end; ++i) {
        if (strcmp(arr[i], min) < 0) { //字符串比较
            min = arr[i];
            min_index = i;
        }
    }

    return min_index;
}
```

```
void Swap(const char **left, const char **right) {
    const char *temp = *left;
    *left = *right;
    *right = temp;
}
```
只交换指针
(有点套娃的意思)
传入的是指针的指针
```Swap(arr + i, arr + min_index);```
语法糖:
arr: char *[]<=>char **
==数组名本身就是一个指向首元素的指针==

temp为*left: char *

2. const的问题
const + double pointer
- const char *arr[]
arr 是个数组,其元素是指向const char的指针==从右往左读==
区别 char * const arr[]

3. 二维数组和指针
语法糖:
int table[][col]: int (*table)[col]
table 是一个指针,指向一个数组,类型为int

table+1 指针移动到下一列
*(table+1)和table+1 指向同一个地方但类型不同
*(table+1):指向数组的指针的解引用=>指向数组的首元素的指针
*(table+1):int [] /int *
*(*(table+1)):int

4. malloc怎么为二维数组申请空间
```
int (*scores)[col]=malloc(col*row*sizeof(*scores))
```

5. 有参数的main函数
```
int main(int argc, char *argv[]);
```
命令行参数
argc: 传入的参数的数量
argv[0]: 程序名
argv[1...argc-1]: 实际传入的命令行参数
argv[argc]: 空指针


### 第十一节课
函数指针
==Functions are first class citizens==
把函数看成一个一等公民
1.   能作为参数
2.   有返回值
3.   能被赋值给变量
4.   能放到数组里面

():函数调用运算符
```
double (*func)(double)
```
理解为该参数是一个指针，该指针指向一个返回double的函数，该函数需要double型参数
#### 能作为参数
```integration = Integrate(low, high, sin);```
将函数作为参数传入时，函数被隐式地转为指针
```double yi = func(xi);```
调用一个函数也会将它隐式地转为指针

```double (*funcs[])(double) = {sin, cos, Square};```
funcs是一个数组,每个元素是一个指针,指向一个接受double返回double的函数

```
void qsort(void *base, size_t nmemb, size_t size,
           int (*compar)(const void *, const void *));
```
传入qsort函数的compar函数必须与原型中的类型一样
```int int_left = *(const int *) left;//强制的类型转换后再解引用```

```
int CompareInts(const void *left, const void *right) {
    int int_left = *(const int *) left;//强制的类型转换后再解引用
    int int_right = *(const int *) right;

    if (int_left < int_right) {
        return -1;
    }

    if (int_left > int_right) {
        return 1;
    }

    return 0;
    }

```

```
int CompareStrs(const void *left, const void *right) {
    const char *const *pp1 = left;
    const char *const *pp2 = right;
    return strcmp(*pp1, *pp2);
}
```

#### 函数能被赋值给变量
```int (*comp)(const void *, const void *) = CompareInts;```

**当要用到函数指针时,推荐给他一个类型别名**
```typedef int (*CompareFunction)(const void *, const void *);```
别名:CompareFunction

#### 函数作为返回值:返回一个函数指针
```
__compar_fn_t GetCompareFunction(bool case_sensitive) {
    return case_sensitive ? &CompareStrs : &CompareStrsCI;
}
```

### 第十二节课
结构体
Overview
1.  结构体
2.  ~~联合体~~
3.  枚举类型

#### 结构体
把相关的信息打包起来作为一个新的类型
```
struct musician{
    char *name;
    char gender;//M:man F:feman

    char *album;

    int c_score;
    int java_score;
    int python_score;

};
```
为一个结构体类型
类型名为struct musician

一种初始化方式(不推荐)
```
struct musician luo={
            "Luo Dayou",
            'M',
            "ZhiHuZheYe",
            0,
            10,
            20,
    };
```

使用命令初始化(==推荐==)
```
    struct musician luo = {
            .name= "Luo Dayou",
            .gender= 'M',
            .album="ZhiHuZheYe",
            .c_score=0,
            .java_score=10,
            .python_score=20,
    };
```

用法:当作简单的类型使用

- "." 运算符:成员运算符
- 结构体的大小的计算:对齐
1. 整体对齐
挑出结构体中占用最大的成员,其占用的大小决定地址开始和最后是多少的倍数

2. 自对齐
每个成员的起始地址要是自身需要占用大小的倍数

**不满足需要填充**
**填充的区域不要去访问**
eg:
```
struct musician{
    char *name;//8
    char gender;//1

   char *album;//8

    int c_score;//4
    int java_score;//4
    int python_score;//4

};

printf("sizeof Musician = %zu\n", sizeof(Musician));//40!=8+1+8+4+4+4
```


- 结构体可以直接相互赋值
```
Musician guo = zhang;
```
==如果牵扯到指针要格外注意==
```
Musician guo = zhang;
guo.name = "Guo";//改变了guo中的name指针的指向,从"zhang chu"变为"Guo"但zhang的name指针指向不会修改
```

- 函数调用中结构体作为参数通常传入指针
可以节省成本
语法糖:
```(*m).name``` <=> ```m->name```(箭头运算符)

#### 枚举类型
可能的情况有限的时候适合用枚举类型
```
typedef enum gender{
    MALE,
    FEMALE,
}Gender;
```
==枚举的类型并不安全,实质上是整型==

### 第十三节课
链表
#### 什么是链表(数据类型/数据结构)
单向链表:由多个结构体组成节点,每个节点的指针指向下一个节点
双向链表:每个节点的指针可以指向上一个节点,也可以指向下一个节点
循环单向链表
循环双向链表:头指针和尾指针不再是空指针

#### 链表的实现
1. 链表(函数)的声明
.h文件 用来知道函数是干嘛的
定义数据类型
函数的声明
2. 链表(函数)的实现
.c文件 用来知道函数是怎么实现的
```
#include "ll.h"
```
include" ":从自己的工程中找

*多文件的编译*
```gcc .\josephus.c .\ll\ll.c -o josephus```
___


1. 链表的节点
含有一个指针,指向另外一个节点
通过指针将链表连起来

==节点类型的定义==
```
struct node {
    int val;
    struct node *next; //==并非循环定义==
};
```
2. 链表结构
两根指针:头和尾
==链表结构的定义==
```
typedef struct list {
    Node *head;
    Node *tail;
} Linkedlist;
```

3. 链表实现
- 初始化
```
void Init(Linkedlist *list) {
    list->head =NULL;
    list->tail =NULL;
}
```
- 在尾部增加一个节点
```
void Append(Linkedlist *list, int val) {
    Node *new_node = malloc(sizeof *new_node);
    if (new_node == NULL) {//空间没有申请成功
        return;
    }
    new_node->val = val;//值传入新节点
    //调整指针的指向
    list->tail->next = new_node; //原来的尾节点的下一条指针，指向new_node
    list->tail = new_node; //原来的尾指针,指向new_node节点
    new_node->next = list->head; //new_node的下一条指针,指向头节点
}
```
==链表相关的问题一定要注意边界情况==
只有一个节点?
链表为空?
if/else 处理特殊情况
找特殊情况和一般情况有没有公共部分,提取出来,使代码更简练

修改后
```
void Append(Linkedlist *list, int val) {
    Node *new_node = malloc(sizeof *new_node);
    if (new_node == NULL) {//空间没有申请成功
        return;
    }
    new_node->val = val;//值传入新节点
    if (IsEmpty(list)) {
        list->head = new_node;
    } else {
        list->tail->next = new_node; //原来的尾节点的下一条指针，指向new_node
    }
    //调整指针的指向
    list->tail = new_node; //原来的尾指针,指向new_node节点
    list->tail->next = list->head; //new_node的下一条指针,指向头节点
}
```

- 打印
```
void Print(Linkedlist *list) {
    Node *node = list->head;
    if (list->head == NULL) {
        return;
    }
    do {
        printf("%d ", node->val);
        node = node->next;
    } while (node != list->head);
}
```

- 删除节点
==要保证操作完的链表类型不变==(仍然为循环单向链表)
```
void Delete(Linkedlist *list, Node *pre_node) {
    if (IsSingleton(list)) { //只有一个节点
        Init(list);
        free(list->head);
        return;
    }
    if (IsEmpty(list)) { //空链表
        return;
    }
    Node *cur_node = pre_node->next;
    Node *next_node = cur_node->next;
    pre_node->next = next_node;

    if (cur_node == list->head) { //删去的是头指针的情况
        list->head = next_node;
    }
    if (cur_node == list->tail) { //删去的是尾指针的情况
        list->tail = pre_node;
    }
    free(cur_node); //删去的节点记得free
}
```
- 释放
```
void Free(Linkedlist *list) {
    while (!IsEmpty(list)) {
        Delete(list, list->head);
    }
}

```

clion中创建.h文件自带下列代码(不要删去)
***head guard***:防止头文件被重复包含
```
#ifndef MY_HEADER_H
#define MY_HEADER_H

// 头文件内容

#endif

```