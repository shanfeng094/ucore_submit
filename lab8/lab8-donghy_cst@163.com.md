# 操作系统lab8实验报告

## 练习1

_完成读文件操作的实现_

完成这个练习, 需要填写`sfs_inode.c`中的`sfs_io_nolock`函数, 这其中要用到两个已经实现的函数, 一个是`sfs_bmap_load_nolock`, 他可以根据内存中的block索引, 得到磁盘上的block号, 另一个是`sfs_buf_op`, 事实上是一个函数指针, 对于可写操作, 指向`sfs_wbuf`, 对于只读操作, 指向`sfs_rbuf`, 负责将buf中的内容写入, 或将内容读出, 写入bug当中. 

实现的过程分为三部分, 开头(可能)不完整的一个block, 结尾(可能)不完整的一个block, 中间的block. 依次对上面三种情况进行处理即可. 

_UNIX的PIPE机制_

[参考资料](http://blog.csdn.net/sunmenggmail/article/details/7888746)

PIPE可以看做是一种特殊的文件, 一个进程将内容写到这个文件当中, 另一个进程从这个文件当中读出内容, 这同时也是符合之前操作系统讲到的read-write系统. 因此只需要实现关于这个特殊文件的read, write, open和close函数即可. 

## 练习2

_完成基于文件系统的执行程序机制的实现_

与原有的代码几乎相同, 不同的地方在于原来从binary读入的数据, 改为由load_icode_read从文件系统读入. 

_UNIX的硬链接和软链接机制_

一个软链接对应一个新的索引节点, 其中的块储存被链接文件的绝对路径; 而硬链接对应着一个目录, 其中的编号就是被链接文件的数据块索引值. 




