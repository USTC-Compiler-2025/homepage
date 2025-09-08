# 建木杯–编译原理创新实验

本比赛是编译原理的创新实验比赛，鼓励同学们积极参加，并有丰厚的现金奖励。

参加方式：组队参加，1-3 人每组

- 参赛人员不限于选了本课程的同学，其他年级、其他专业的学生也鼓励参加（同学们也可以帮忙传播该比赛）

实验时间：现在 - 2024 三月底（暂定）

比赛内容：根据课堂所学知识和[实验框架](https://cscourse.ustc.edu.cn/vdir/Gitlab/compiler_staff/2023ustc-jianmu-compiler/-/tree/master)，开发一个针对 SysY 语言的龙芯后端编译器，并通过相关测试样例

考核标准：测试样例通过情况 + 测试样例性能分数 + 答辩分数 + bonus（暂定）

## SysY 语言

SysY 语言是编译系统设计赛要实现的编程语言。由 C 语言的一个子集扩展而成。每个 SysY 程序的源码存储在一个扩展名为 sy 的文件中。该文件中有且仅有一个名为 main 的主函数定义，还可以包含若干全局变量声明、常量声明和其他函数定义。SysY 语言支持 int/float 类型和元素为 int/float 类型且按行优先存储的多维数组类型，其中 int 型整数为 32 位有符号数；float 为 32 位单精度浮点数；const 修饰符用于声明常量。SysY 支持 int 和 float 之间的隐式类型，但是无显式的强制类型转化支持。

SysY 语言本身没有提供输入/输出 (I/O) 的语言构造，IO 是以运行时库方式提供，库函数可以在 SysY 程序中的函数内调用。部分 SysY 运行时库函数的参数类型会超出 SysY 支持的数据类型，如可以为字符串。SysY 编译器需要能处理这种情况，将 SysY 程序中这样的参数正确地传递给 SysY 运行时库。有关在 SysY 程序中可以使用哪些库函数，请参见 SysY 运行时库文档。

相关文档：

- 语言定义：<https://cscourse.ustc.edu.cn/vdir/Gitlab/compiler_staff/jianmu-supplemental/-/blob/master/SysY2022%E8%AF%AD%E8%A8%80%E5%AE%9A%E4%B9%89-V1.pdf>
- 运行时库：<https://cscourse.ustc.edu.cn/vdir/Gitlab/compiler_staff/jianmu-supplemental/-/blob/master/SysY2022%E8%BF%90%E8%A1%8C%E6%97%B6%E5%BA%93-V1.pdf>
- I/O 相关实现：<https://cscourse.ustc.edu.cn/vdir/Gitlab/compiler_staff/jianmu-supplemental/-/tree/master/%E5%A4%96%E9%83%A8%E5%87%BD%E6%95%B0>

## 比赛内容

根据课堂所学知识和实验框架，开发一个针对 SysY 语言的龙芯后端编译器，并通过相关测试样例并汇报性能分数。

开发该编译器至少涉及以下内容：

- 设计和实现语言解析器得到具体语法树
- 设计抽象语法树（AST），并将具体语法树转化为 AST
- 基于 AST，进行中间代码生成
- 基于中间代码生成龙芯汇编

注意：我们上课使用的实验框架可能不能完全支持全功能的 SysY 语言，可以视情况进行修改。

我们将视情况提供原生的龙芯环境，方便参赛队伍进行调试和开发。

### 测试样式

测试样例分为 func 和 perf

- 对于 func 的测试样例，其得分要点为通过率，正确通过数目越高得分越高。
- 对于 perf 的测试样例，其得分要点为性能（执行时间），性能越高则得分越高。
  - 提高性能涉及各种优化，对性能提升显著的优化主要有以下：**Mem2Reg**，**寄存器分配**，**循环相关的优化**

优先级上：func 的通过率 > perf 的分数

测试样例链接：<https://cscourse.ustc.edu.cn/vdir/Gitlab/compiler_staff/jianmu-supplemental/-/tree/master/%E6%B5%8B%E8%AF%95%E6%A0%B7%E4%BE%8B>

### 考核标准

- 测试样例通过情况：汇报通过率
- 测试样例性能分数：汇报性能分数
- 答辩分数：评委打分
- Bonus：评委打分

## 奖项

- 一等奖：3000￥
- 二等奖：1500￥
- 三等价：800￥
- 积极参与奖若干（小礼品或其他）

## Bonus

Bonus 分为两种类型：

- 指令类型以及优化 pass 丰富程度
- SysY 语言支持完整程度

### 指令类型以及优化 pass 丰富程度

针对中间代码、后端生成的指令类型以及优化 pass 丰富程度会提供额外的加分。

### SysY 语言支持完整程度

针对 SysY 语言，在 <https://gitlab.eduxiji.net/nscscc/compiler2023> 上还有多达上百个测试样例，有以下四个目录：

- final_performance
- functional
- hidden_functional
- performance

对于这些测试样例，可以视情况进行测试，并在答辩时提供通过情况（如下），针对高通过率的队伍，会提供额外的加分。

```shell
* final_performance (通过率: 10/37，总执行时间：60 sec)
* functional (通过率: 100/100)
* hidden_functional (通过率: 30/40)
* performance (通过率: 10/59，总执行时间：102 sec)
```

## 报名方式

组队参加，至多三人一组，将报名信息发送至 gpzlx1@mail.ustc.edu.cn。主题为"编译创新实验报名"，内容为参赛同学学号、姓名、队长等相关信息。

相关 QQ 群：648929105

![编译创新实验群二维码](assets/编译创新实验群二维码.png)

## 声明

针对 SysY 语言，网上已经有很多非常优秀的开源实现。如果**借鉴**或**参考**了这些开源实现，须在答辩时主动说明参考对象以及在其上的相关修改。
