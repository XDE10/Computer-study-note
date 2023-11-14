---
tags:
  - shell
---

定义变量
```shell
foo=bar
echo $foo
>>bar
```
注意空格的使用！空格是用于分隔参数的保留字符
如 ``foo = bar``，程序会把 ``=`` 和 ``bar`` 作为参数传给 ``foo`` 程序

定义字符串变量——用**双引号**或**单引号**
例如 ``echo "world"`` 或 ``echo 'hello'`` 
对于纯文本字符串，两种方法等价，对于其余字符串则不相同
```shell
echo "Value is $foo"
>>Value is bar
```

```shell
echo 'Value is $foo'
>>Value is $foo
```
双引号中的变量被替换，单引号中的变量不会被替换

定义函数
```shell
vim mcd.sh
```
进入 ``mcd.sh`` 并定义 ``mcd`` 函数
```shell
mcd () {
	mkdir -p "$1"
	cd "$1"
}
```
注意：按 ``i`` 可进入 ``insert`` 可编辑模式；按 ``Esc`` 后再按 ``Shift`` + ``z`` （两次 ``z`` ）可保存修改内容并退出
```shell
source mcd.sh
```
会在Shell中加载脚本并执行

``grep`` 命令——命令用于查找文件里符合条件的字符串或正则表达式
```shell
grep foobar mcd.sh
echo $?
>>1
```
返回值为1，说明 ``grep`` 没有成功执行

``mcd`` 命令——会创建 ``test`` 文件夹并进入其中
```shell
mcd test
```

``$?`` 命令——可以获取上条命令的错误代码（返回值）
```shell
echo "Hello"
>>Hello
echo $?
>>0
```
``0`` 代表正常，没有出错

``true`` 的返回值为 ``0`` , ``false`` 的返回值为 ``1``

``$_`` 命令——会获取上条命令的最后一个参数
```shell
mkdir test
cd $_
当前目录变为 test
```

``rdir`` 命令——删除空的目录

``!!`` 命令——会被刚刚尝试的命令取代

逻辑运算符：与(&&)、或(||)、非(!)

短路运算法则(惰性运算)
```shell
false || echo "Hello"
>>Hello
```

```shell
true || echo "Hello"
>>
```

```shell
true && echo "Hello"
>>Hello
```

```shell
false && echo "Hello"
>>
```

在同一行内用 ``;`` 连接命令

把命令存到变量中
```shell
foo=$(pwd)
echo $foo
>>/home/xuedinge
```
上述程序获取 ``pwd`` 命令的输出，并将其存到 ``foo`` 变量中

命令替换
```shell
echo "We are in $(pwd)"
>>We are in /home/xuedinge
```

进程替换
```shell
cat <(ls) <(ls ..)
>>hello.txt
hello2.txt
last-modified.txt
mcd.sh
test
xuedinge
```
将两个文件连接起来

``find`` 命令——用于在指定目录下查找文件和目录
``find . -name file.txt``
查找当前目录下名为 ``file.txt`` 的文件




