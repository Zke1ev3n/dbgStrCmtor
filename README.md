# dbgStrCmtor

最近因为研究内容的关系,需要经常分析加固和混淆过的elf文件.真是比较耗费精力的事情啊.特别是ida pro与od不一样的, 寄存器窗口不会直接把字符串显示出来.所以,经常需要双击地址,再双击地址一直到一个字符串. 才知道当前在处理什么文件,或者处理什么内容. 
函数更是这样了,初步调试很多函数看到入参和出参就能猜到函数功能了. 双击再双击是在麻烦, 如果能在每个调用函数的时候能直接看到入参和出参就好了. 
我们对于一些常见的Hash函数(SHA1,MD5等),加解密函数(AES等), 通常是通过一些常量和一些固定的汇编逻辑来识别的. 如果能比较快速的识别出来哪些代码在运行的是Hash函数/加解密函数的逻辑,也能节省很多调试时间. 
于是做了这么一个程序. 包含三个功能点:
1.	识别字符串,以及字符串的指针(或者多层指针最终指向一个字符串),并且把字符串内容以comment的形式附加到指令处.
2.	记录函数入参与出参,并且以comment的形式附加到函数的调用处. 
3.	识别各种常见的Hash函数以及加解密函数(的常量),并且以comment形式附加到识别出来的指令处. 
