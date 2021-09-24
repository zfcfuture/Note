### Text、Data、Bss

#### 1.  a.out

linux下编译链接程序，如果不加-o参数，输出文件名默认为a.out（assembler output），代表的是<span style="color:red">汇编程序的输出</span>。早期类unix系统中，a.out是一种<span style="color:green">输出格式</span>，用于可执行文件。之后，人们编写了链接器，程序的创建是<span style="color:red">先编译后链接</span>输出保存到a.out中。因为构建a.out的复杂性，现在a.out格式被普遍使用的ELF（Executable and Linking Format）格式所替代，但输出文件名仍旧是a.out，所以我们现在看到的a.out是一个可执行文件，而不再是文件格式.

#### 2.  段（Segment）

不管是a.out格式、ELF格式还是COFF格式，这些不同的格式具有一个共同的概念，那就是段（Segment），在unix中，它表示一个==二进制文件相关的内容块==。一个可执行文件有三个段：文本段（代码段）、数据段以及BSS段（Block Started by Symbol），可用size命令查看段的大小

- Text：存放程序指令
- Data：存放所有<span style="color:red">经过初始化的</span>全局变量和静态变量
- BSS：存放<span style="color:red">未经初始化的</span>全局变量和静态变量