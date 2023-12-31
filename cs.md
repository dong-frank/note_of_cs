# 本文为CS笔记
- [本文为CS笔记](#本文为cs笔记)
  - [插件](#插件)
  - [Powershell\&Windows terminal](#powershellwindows-terminal)
    - [各种快捷键](#各种快捷键)
    - [命令](#命令)
  - [git 版本管理系统](#git-版本管理系统)
    - [指令](#指令)
    - [与GitHub 的互动](#与github-的互动)
  - [Markdown](#markdown)
    - [基础语法](#基础语法)
  - [eg:](#eg)
    - [进阶语法](#进阶语法)
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

## 插件
1. caps2ctrl
2. tabnine
---

## Powershell&Windows terminal
### 各种快捷键
**ctrl =**/**ctrl -** :界面的放大/缩小
**alt shift -**:竖直分栏
**alt shift =**:水平分栏
**ctrl shift f**:查找
**ctrl shift p**:打开命令菜单
**ctrl r**:历史记录查找
**ctrl l**:指针回到最上

---


### 命令
```
cd d:\freshman\All_notes //绝对路径
```

```
cd .\All_notes  //相对路径
```

```
pushd
popd
//存放和取出命令,可以多次使用
```

```
cd ~  //约定,回到用户目录
```

```
mkdir dir  //新建文件夹
```

```
ni item  //新建文件
```

```
rm dir  //删除(不可逆*慎用*)
```

```
ls
dir
//显示目录
```

```
cat c:\users\frank\.ssh\id_rsa.pub  
//显示文件内容
```

```
mv item item2 //移动或重命名
```

```
man ls  //查看手册*学习命令的好办法*
```
---

## git 版本管理系统

### 指令
1. 配置
```
git config --global user.name"Frank"
git config --global user.email"dongshen_rao@smail.nju.edu.cn"
//配置用户名和邮件地址

git config --list  //查看配置
```
2. 新建git仓库
```
git init
```

3. 添加文件到暂存区
```
git add filename
git add .  || git add -A  //添加所有文件
```

4. 提交暂存区的修改
```
git commit -m"message"
```
*tips:养成写好message的习惯,有时能节省很多时间*
==记得ctrl s 保存==

5. 查看git仓库
```
git status
```

6. 查看提交日志
```
git log
//键入:q 退出
```

7. 版本切换
```
git checkout version
```

8. 新建分支
```
git checkout -b<branch name>
```

9. 查看分支信息
```
git branch
```

10. 合并分支
```
git merge name_of_branch
```

---

### 与GitHub 的互动
1. SSH-key 的生成
```
cd ~/.ssh
ssh-keygen -t rsa -C"your email"
cat id_rsa.pub  //显示公钥
```

2. 关联SSH-key 与GitHub
**将公钥黏贴至GitHub的个人页面中**

3. 将本地库上传至GitHub
- GitHub网页选择[create a new repository]
- 将[push an existing repository from the command line]中的三条命令一次在git bash 中执行
```
git remote add origin git@github.com:dong-frank/1.git
git branch -M main
git push -u origin main
```
```
git pull origin master –-allow-unrelated-histories
```

1. 克隆仓库到本地
```
git clone 复制ssh
```

1. 拉取远程仓库数据并合并到当前分支
```
git pull  //= git fetch + git merge
```

1. 推送本地仓库的commit记录到远程仓库
```
git push
```
---


## Markdown
### 基础语法

1. 标题
```
# 这是一个一级标题
## 这是一个二级标题
...
###### 这是一个六级标题
```

2. 强调
```
**所强调的内容**
```
eg:**好好学习天天向上**

3. 斜体
```
*内容*
```
eg:*斜了*

4. 斜体并强调
```
***内容***
```

5. 高亮
```
==内容==
```
eg:==内容==

6. 代码块
```
```

7. 引用
```
> 引用的内容
```
eg:
> 书籍是人类进步的阶梯
> > 引用可嵌套

8. 无序列表
```
- 内容
```
eg:
- 内容

9. 有序列表
```
1. 内容
```

10. 上标
```
^上标^
```
eg:2^10^=1024

11. 下标
```
~下标~
```
eg:H~2~O

12. 注释
```
> 今日我们相聚于此, 是为了学习 Markdown 的使用, 它的教程对于全体「观众」而言, 值得足足两个硬币的支持鼓励![^1]

[^1]: 沃兹·基·硕德 改编自「公鸡」普契涅拉.
```

13. 链接
```
[链接内容](链接地址)
```
eg:[markdown教程](https://github.com/Sakiyary/Markdown-Typora-VSCode-Doc#user-content-fn-1-8f4a1227be7fc551eec52f739032ce39)

14. 任务列表
```
- [ ] 任务名
- [x] 任务名
```
eg:
- [ ] 完成markdown使用笔记
- [x] 摆烂

15. 表格
```
| 学号 | 姓名  | 年龄 |
| :--- | :---: | ---: | (引号的位置代表着 左对齐, 居中, 右对齐)
|114514|田所|24|
|1919810|浩三|25|
```
eg:

| 学号 | 姓名  | 年龄 |
| :--- | :---: | ---: |
|114514|田所|24|
|1919810|浩三|25|

16. 图片
直接拖入复制

17. 分割线
```
---
```
eg:
---
---
---

18. emoji表情
从[emoji大全](https://emojipedia.org/zh)中复制❤️

19. 删除线
```
~~~内容~~~
```
eg:~~~误~~~

20. 空格
```
&nbsp;
```

---

### 进阶语法
1. 目录
若使用 VS Code 搭配 Markdown All in One 扩展, 可在 VS Code 的命令面板 (即 VS Code Command Palette) 输入 Create Table of Contents 自动生成目录, 且可在扩展设置中细调目录参数.

2. 内嵌HTML代码

用 "<> </>" 包围

- [ ] 学习HTML



---
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