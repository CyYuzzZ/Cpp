# 1. 内存相关
## 1.1 new和malloc的区别

- 属性
> new/delete是C++关键字，需要编译器支持。
> 
> malloc/free是库函数，需要头文件支持。

- 指定内存块大小
> 使用new操作符申请内存分配时无须指定内存块的大小，编译器会根据类型信息自行计算。
> 
> malloc需要显式地指出所需内存的尺寸。

- 返回
> 1. new操作符内存分配成功时，返回的是对象类型的指针，类型严格与对象匹配，无须进行类型转换，故new是符合类型安全性的操作符。
> 
>    malloc内存分配成功返回void * ，需要通过强制类型转换将void* 指针转换成我们需要的类型。
> 
> 2. new内存分配失败时，会抛出bac_alloc异常。
> 
>    malloc分配内存失败时返回NULL。

- 内存位置
> new操作符从自由存储区（free store）上为对象动态分配内存空间，而malloc函数从堆上动态分配内存。
> 
> 自由存储区是C++基于new操作符的一个抽象概念，凡是通过new操作符进行内存申请，该内存即为自由存储区。
> 
> 堆是操作系统中的术语，是操作系统所维护的一块特殊内存，用于程序的内存动态分配，C语言使用malloc从堆上分配内存，使用free释放已分配的对应内存。
> 
> 自由存储区不等于堆，如上所述，布局new就可以不位于堆中。

- 构造/析构函数

调用operator new 函数（对于数组是operator new[]）分配一块足够大的，原始的，未命名的内存空间以便存储特定类型的对象。

> new：1）调用operator new函数，申请足够的内存（通常底层使用malloc实现）；2）调用构造函数，初始化成员变量；3）返回指向该类型的指针。
> 
> delete：1）调用对象的析构函数；2）编译器调用operator delete（或operator delete[]）函数释放内存（通常底层使用free实现）。
> 
> malloc/free是库函数，只能动态的申请和释放内存，无法强制要求其做自定义类型对象构造和析构工作。

- 重载
> C++允许重载new/delete操作符，特别的，布局new的就不需要为对象分配内存，而是指定了一个地址作为内存起始区域，new在这段内存上为对象调用构造函数完成初始化工作，并返回此地址。
> 
> malloc不允许重载。




## 1.2 malloc的底层实现


# 2. 在1G内存的计算机中能否malloc(1.2G)？为什么？


# 2. C语言检索内存情况 内存分配的方式⭐⭐⭐







# 2. 指针与引用的相同和区别；如何相互转换？⭐⭐⭐⭐⭐




# 2. extern”C” 的作用⭐⭐⭐


# 2. 头文件声明时加extern定义时不要加 因为extern可以多次声明，但只有一个定义⭐⭐⭐⭐


# 2. 函数参数压栈顺序，即关于__stdcall和__cdecl调用方式的理解⭐⭐⭐


# 2. 重写memcpy()函数需要注意哪些问题⭐⭐


# 2. 数组到底存放在哪里⭐⭐⭐


# 2. struct和class的区别 ⭐⭐⭐⭐⭐

# 2. char和int之间的转换；⭐⭐⭐

# 2. static的用法（定义和用途）⭐⭐⭐⭐⭐

# 2. const常量和#define的区别（编译阶段、安全性、内存占用等） ⭐⭐⭐⭐

# 2. volatile作用和用法 ⭐⭐⭐⭐⭐

# 2. 有常量指针 指针常量 常量引用 没有 引用常量⭐⭐⭐

# 2. 没有指向引用的指针，因为引用是没有地址的，但是有指针的引用⭐⭐⭐

# 2. c/c++中变量的作用域⭐⭐⭐⭐⭐

# 2. c++中类型转换机制？各适用什么环境？dynamic_cast转换失败时，会出现什么情况？⭐⭐⭐

# 2. 

# 2. 

# 2. 

# 2. 
