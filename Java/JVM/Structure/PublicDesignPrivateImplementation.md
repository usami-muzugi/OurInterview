# 公有设计，私有实现 

到此为止，本书简单描绘了 Java 虚拟机应有的共同外观： Class 文件格式以及字节码指令集等。这些内容与硬件、操作系统和 Java 虚拟机的独立实现都是密切相关的，虚拟机实现者可能更愿意把它们看做是程序在各种 Java 平台实现之间互相安全地交互的手段，而多于一张需要精确跟随的计划蓝图。
理解公有设计与私有实现之间的分界线是非常有必要的， Java 虚拟机实现必须能够读取Class 文件并精确实现包含在其中的 Java 虚拟机代码的语义。拿着《 Java 虚拟机规范》一成不变地逐字实现其中要求的内容当然是一种可行的途径，但实现者在本规范约束下对具体实现做出修改和优化也是完全可行，并且也推荐这样做的。只要优化后 Class 文件依然可以被正确读取，并且包含在其中的语义能得到保持，那实现者就可以选择任何方式去实现这些语义，虚拟机后台如何处理 Class 文件完全是实现者自己的事情，只要它在外部接口上看起来与规范描述的一致即可①。
实现者可以使用这种伸缩性来让 Java 虚拟机获得更高的性能、更低的内存消耗或者更好的可移植性，选择哪种特性取决于 Java 虚拟机实现的目标和关注点是什么，虚拟机实现的方式主要有以下两种： 

* 将输入的 Java 虚拟机代码在加载时或执行时翻译成另外一种虚拟机的指令集
* 将输入的 Java 虚拟机代码在加载时或执行时翻译成宿主机 CPU 的本地指令集（有时候被称 Just-In-Time 代码生成或 JIT 代码生成）

精确定义的虚拟机和目标文件格式不应当对虚拟机实现者的创造性产生太多的限制， Java 虚拟机是被设计成可以允许有众多不同的实现，并且各种实现可以在保持兼容性的同时提供不同的新的、有趣的解决方案。 























































