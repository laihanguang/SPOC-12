## 12.2 进程创建

###5. 请在ucore启动时显示空闲线程（idleproc）和初始进程(initproc)的进程控制块中的“pde_t *pgdir”的内容。它们是否一致？为什么？

是一致的，都是0x274000。

因为idleproc与initproc都是直接使用操作系统启动时使用的那个页表，它们的cr3都是0x274000。

在ucore的proc.c中的这行代码

proc->cr3 = boot_cr3; 

将cr3设置为boot_cr3。



