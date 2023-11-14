---
tags:
  - vim
---

Vim 是基于模态（Modal）的编辑器，有多种模式

normal 模式---·`` i`` --->insert 模式---`` Esc`` --->normal模式

Vim 编辑器的模式（按 ``Esc`` 回到 ``normal`` 模式）
normal 模式：用来移动光标，阅读，文件切换

insert 模式：输入

replace 模式：直接覆盖文本（``R``）

selection 模式：visual 模式（``v``），visual line 模式（``Ctrl v``），visual block 模式（``shift v``）

command line 模式（``:``）

通常把 ``Caps`` 作为 ``Esc`` 的映射键

输入 vim 或 vim + 文件名 进入 vim 编辑器

输入 ``:w`` 可以保存文件，输入 ``:q`` 退出 vim

``:`` 中输入 ``help`` + ``快捷键`` 可以获得其说明

buffer, window, tab
buffer ：文件在内存中的缓存数据
window ：负责展示 buffer 数据且不会影响 buffer
tab ：是 window 的集合

Buffer 负责保存数据，Window 负责展示数据，Tab 为 Window 提供排版布局
Buffer 和 Tab 对 Window 总是一对多的关系

``sp`` 创建新的 ``window`` 
``:q`` 退出当前 ``window`` ，``:qa`` 可以退出所有 ``window``

Vim 的接口是一种编程语言，意味着不同的按键组合有不同的效果，可以编写程序和vim交谈 

``u`` ：撤销
相反，``Ctrl + r`` ：重做

移动命令—— normal 模式
normal 模式下，hjkl 控制光标，h 左，j 下，k 上，l 右

编辑命令—— insert 模式
``o`` ：在光标下方新开一行并进入 ``insert`` 模式
``O`` ：在光标上方新开一行并进入 ``insert`` 模式
``d + 单词首字母`` ：光标在单词首字母上，可以删除整个单词（delete）
``c`` ：删除并进入 ``insert`` 模式（change）

按某个编辑键两次，会作用于整行

``x`` ：删除光标所在的字符
``r + 字符`` ：替换光标所在字符

``y`` ：复制
``p`` ：粘贴

