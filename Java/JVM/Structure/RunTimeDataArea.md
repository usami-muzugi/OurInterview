# 运行时数据区

Java 虚拟机定义了若干种程序运行期间会使用到的运行时数据区，其中有一些会随着虚拟机启动而创建，随着虚拟机退出而销毁。另外一些则是与线程一一对应的，这些与线程对应的数据区域会随着线程开始和结束而创建和销毁。 

## PC 寄存器

Java 虚拟机可以支持多条线程同时执行，每一条 Java虚拟机线程都有自己的 PC（ Program Counter）寄存器。在任意时刻，一条 Java 虚拟机线程只会执行一个方法的代码，这个正在被线程执行的方法称为该线程的当前方法（ Current Method）。如果这个方法不是 native 的，那 PC 寄存器就保存 Java 虚拟机正在执行的字节码指令的地址，如果该方法是 native 的，那 PC 寄存器的值是 undefined。 PC 寄存器的容量至少应当能保存一个returnAddress 类型的数据或者一个与平台相关的本地指针的值。

##  Java 虚拟机栈

每一条 Java 虚拟机线程都有自己私有的 Java 虚拟机栈（ Java Virtual Machine Stack）①，这个栈与线程同时创建，用于存储栈帧（ Frames）。 Java 虚拟机栈的作用与传统语言（例如 C 语言）中的栈非常类似，就是用于存储局部变量与一些过程结果的地方。另外，它在方法调用和返回中也扮演了很重要的角色。因为除了栈帧的出栈和入栈之外， Java 虚拟机栈不会再受其他因素的影响，所以栈帧可以在堆中分配②， Java 虚拟机栈所使用的内存不需要保证是连续的。Java 虚拟机规范允许 Java 虚拟机栈被实现成固定大小的或者是根据计算动态扩展和收缩的。如果采用固定大小的 Java 虚拟机栈设计，那每一条线程的 Java 虚拟机栈容量应当在线程创建的时候独立地选定。 Java 虚拟机实现应当提供给程序员或者最终用户调节虚拟机栈初始容量的手段，对于可以动态扩展和收缩Java 虚拟机栈来说，则应当提供调节其最大、最小容量的手段。Java 虚拟机栈可能发生如下异常情况：

* 如果线程请求分配的栈容量超过 Java 虚拟机栈允许的最大容量时， Java 虚拟机将会抛出一个 StackOverflowError 异常。
* 如果 Java 虚拟机栈可以动态扩展，并且扩展的动作已经尝试过，但是目前无法申请到足够的内存去完成扩展，或者在建立新的线程时没有足够的内存去创建对应的虚拟机栈，那 Java 虚拟机将会抛出一个OutOfMemoryError 异常。 

## Java 堆

在 Java 虚拟机中，堆（ Heap）是可供各条线程共享的运行时内存区域，也是供所有类实例和数组对象分配内存的区域。Java 堆在虚拟机启动的时候就被创建，它存储了被自动内存管理系统（ Automatic Storage Management System，也即是常说的“ Garbage Collector（垃圾收集器）”）所管理的各种对象，这些受管理的对象无需，也无法显式地被销毁。本规范中所描述的 Java 虚拟机并未假设采用什么具体的技术去实现自动内存管理系统。虚拟机实现者可以根据系统的实际需要来选择自动内存管理技术。 Java 堆的容量可以是固定大小的，也可以随着程序执行的需求动态扩展，并在不需要过多空间时自动收缩。 Java 堆所使用的内存不需要保证是连续的。Java 虚拟机实现应当提供给程序员或者最终用户调节 Java 堆初始容量的手段，对于可以动态扩展和收缩 Java 堆来说，则应当提供调节其最大、最小容量的手段。

Java 堆可能发生如下异常情况：

* 如果实际所需的堆超过了自动内存管理系统能提供的最大容量，那 Java 虚拟机将会抛出一个OutOfMemoryError 异常。

## 方法区

在 Java 虚拟机中，方法区（ Method Area） 是可供各条线程共享的运行时内存区域。方法区与传统语言中的编译代码储存区（ Storage Area Of Compiled Code）或者操作系统进程的正文段（ Text Segment）的作用非常类似，它存储了每一个类的结构信息，例如运行时常量池（ Runtime Constant Pool）、字段和方法数据、构造函数和普通方法的字节码内容、还包括一些在类、实例、接口初始化时用到的特殊方法。方法区在虚拟机启动的时候被创建，虽然方法区是堆的逻辑组成部分，但是简单的虚拟机实现可以选择在这个区域不实现垃圾收集。这个版本的 Java 虚拟机规范也不限定实现方法区的内存位置和编译代码的管理策略。方法区的容量可以是固定大小的，也可以随着程序执行的需求动态扩展，并在不需要过多空间时自动收缩。 方法区在实际内存空间中可以是不连续的。Java 虚拟机实现应当提供给程序员或者最终用户调节方法区初始容量的手段，对于可以动态扩展和收缩方法区来说，则应当提供调节其最大、最小容量的手段。

方法区可能发生如下异常情况：

* 如果方法区的内存空间不能满足内存分配请求，那 Java 虚拟机将抛出一个OutOfMemoryError 异常。

## 运行时常量池

运行时常量池（ Runtime Constant Pool）是每一个类或接口的常量池（ Constant_Pool）的运行时表示形式，它包括了若干种不同的常量：从编译期可知的数值字面量到必须运行期解析后才能获得的方法或字段引用。运行时常量池扮演了类似传统语言中符号表（ Symbol Table）的角色，不过它存储数据范围比通常意义上的符号表要更为广泛。每一个运行时常量池都分配在 Java 虚拟机的方法区之中（ §2.5.4），在类和接口被加载到虚拟机后，对应的运行时常量池就被创建出来。在创建类和接口的运行时常量池时，可能会发生如下异常情况：

* 当创建类或接口的时候，如果构造运行时常量池所需要的内存空间超过了方法区所能提供的最大值，那 Java 虚拟机将会抛出一个 OutOfMemoryError 异常。

关于构造运行时常量池的详细信息，可以参考“加载、 链接和初始化”的内容。

## 本地方法栈

Java 虚拟机实现可能会使用到传统的栈（通常称之为“ C Stacks”）来支持 native 方法（ 指使用 Java 以外的其他语言编写的方法）的执行，这个栈就是本地方法栈（ Native Method Stack）。当 Java 虚拟机使用其他语言（例如 C 语言）来实现指令集解释器时，也会使用到本地方法栈。如果 Java 虚拟机不支持 natvie 方法，并且自己也不依赖传统栈的话，可以无需支持本地方法栈，如果支持本地方法栈，那这个栈一般会在线程创建的时候按线程分配。 Java 虚拟机规范允许本地方法栈被实现成固定大小的或者是根据计算动态扩展和收缩的。如果采用固定大小的本地方法栈，那每一条线程的本地方法栈容量应当在栈创建的时候独立地选定。一般情况下， Java 虚拟机实现应当提供给程序员或者最终用户调节虚拟机栈初始容量的手段，对于长度可动态变化的本地方法栈来说，则应当提供调节其最大、最小容量的手段。本地方法栈可能发生如下异常情况：

* 如果线程请求分配的栈容量超过本地方法栈允许的最大容量时， Java 虚拟机将会抛出一个StackOverflowError 异常。
* 如果本地方法栈可以动态扩展，并且扩展的动作已经尝试过，但是目前无法申请到足够的内存去完成扩展，或者在建立新的线程时没有足够的内存去创建对应的本地方法栈，那 Java 虚拟机将会抛出一个 OutOfMemoryError 异常。 







































