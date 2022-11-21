# 栈

**一种后进者先出，先进者后出的数据结构**。
<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="https://raw.githubusercontent.com/hongguangli/Figures/main/20221202163124.png" width=500>
</center>

从栈的操作特性上来看，栈是一种“操作受限”的**线性表**，只允许在**一端插入和删除数据**。
栈主要包含两个操作，**入栈**和**出栈**，也就是在**栈顶插入**一个数据和从**栈顶删除**一个数据。
栈既可以用数组来实现，也可以用链表来实现。用**数组实现**的栈，我们叫作**顺序栈**，用**链表实现**的栈，我们叫作**链式栈**。

在入栈和出栈过程中，只需要一两个临时变量存储空间，所以**空间复杂度是 O(1)**。