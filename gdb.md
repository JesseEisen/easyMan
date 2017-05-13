## gdb

### breakpoint
    
    b [function|lineno]   创建断点
    i b                   查看断点
    disable [breakpoint number] 关闭指定断点
    clear [lineno|function name] 清除指定断点

### example variable
    
    disp [variable]  创建需要监控的变量
    info display     查看当前有多少个变量
    disable display [number] 关闭指定变量
    undisplay [number] 删除掉指定变量

同时可以使用print或者printf来查看指定变量的值。

    print i
    printf "%08x\n", i

### Stepping methods

退出当前的函数并返回调用的函数，使用`finish`
以汇编指令为单位的单步，使用`stepi`
执行到指定的地点，使用`advance`, 这个命令也可理解为继续执行到这个临时断点

### Changing Variable

    set (i = 20)
    set variable i = 20

### Watchpoints

这个经常用在你想知道什么时候这个变量被改变了。

    watch i
    info watch   查看当前有哪些变量被watch了
    delete [number] 删除指定的变量
    rwatch      检测什么时候变量被读取
    awatch      检测什么时候变量被读取和写入

### Attach to a running process

用ps查看到当前运行进程的id，
    
    attach pid

接着可以使用bt或者finish来进行更快的运行，到达你想要查看的那个函数

### display registers and assembly

在tui模式下，可以使用如下的命令

    layout src   标准模式，源代码在上面，命令在下面
    layout asm   asm在上，命令在下
    layout split 三个窗口，源代码，asm，命令
    layout reg   寄存器相关

可以设置asm的语法，intel还是att。 

    set disassembly-flavor intel
    layout src
    layout split   后面两个用于已经打开了asm窗口

### reverse

    reverse-step
    reverse-next

 如果出现了`Target child dose not support this command`
    
    target record-full
    target record  #old version

### show all function

    set logging on    # collect trace in gdb.txt
    set confirm off   # do not confirm all the break
    rbreak .          # set a breakpoint on each function 

 另一个方法是使用record

    record function-call-history /ilc

在这个之前，需要使用record btrace. 不过有时候会不支持

    
