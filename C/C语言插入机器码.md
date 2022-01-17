### C语言插入机器码

#### 1.  基于Risc-V64

在riscv架构中，一个**字**的大小是==4个字节==，即32位，可直接使用<font color=red>.word</font>的方式插入，具体如下：

```c
// 已知ebreak的机器码为0x00100073
// 采用内嵌汇编的方式插入
switch(mode)
{
    case 3: __asm__ __vlatile__(".word 0x00100073"); break;
    case 2: __asm__ __vlatile__(".word 0x00100073"); break;
    case 1: __asm__ __vlatile__(".word 0x00100073"); break;
}
```

