#Linux GCC常用命令

@(ubuntu)

[TOC]

---


##1.简单编译

>实质上，上述编译过程是分为四个阶段进行的，即预处理(也称预编译，Preprocessing)、编译(Compilation)、汇编 (Assembly)和连接(Linking)。

```
gcc test.c
```
生成一个a.out文件，运行`./a.cout`即可查看输出结果

##2.1预处理

```
gcc -E test.c -o test.i 或 gcc -E test.c
```

##2.2编译为汇编代码(Compilation)

```
gcc -S test.i -o test.s
```

##2.3汇编(Assembly)

```
gcc -c test.s -o test.o
```

##2.4连接(Linking)

```
gcc test.o -o test
```

##3.多个程序文件的编译

```
gcc -c test1.c -o test1.o
gcc -c test2.c -o test2.o
gcc test1.o test2.o -o test
```

##4.输出结果

    ./test

