---
title: "sed"
date: 2013-08-17 07:32
---


## 格式 ##

	sed options script file

	* -e script
	* -f file
	* -n


## 替换(substitute) ##

	s/pattern/replacement/flag

	* 数字	表明新文本将替换第几处模式匹配的地方
	* g		所有匹配的都替换
	* p		原来的内容也打印出来
	* w file将替换的结果写到文件中



## 限制行数 ##

	* 数字	指定行数
	* 数字1,数字2	限定范围
	* $表示结尾行
	*
	* 其实还可以使用文本模式过滤器
	* /pattern/command 
	* eg. $ sed '/tankywoo/s/bash/csh/' /etc/passwd


## 删除行 ##

	sed 'd' mydata		#删除全部
	sed '1d' mydata		#删除第一行
	这个同样也可以用于上面的模式匹配


## 插入和附加 ##

	插入i会在指定行前插入一个新行
	插入a会在指定行后插入一个新行
	echo "Test Line 2" | sed 'i\Test Line 1'
	echo "Test Line 2" | sed 'a\Test Line 1'


## 修改 ##

	字符c是修改指定行的整行内容
	sed '3c\'		#修改第三行


## 转换 ##

	字符y是进行单个字符映射的转换，且是全局的
	sed 'y/abc/123' mydata
	会将所有的a转换成1，b转换成2，c转换成3


## 打印 ##

	* p 打印问本行
	* #	打印行号
	* l	列出行


## 文件操作 ##

	* w	写入文件
	* r	读入文件


## 资料 ##

* [man手册](http://unixhelp.ed.ac.uk/CGI/man-cgi?sed)
* [sed](http://sed.sourceforge.net/sed1line_zh-CN.html)
* [sed](http://www.grymoire.com/Unix/Sed.html)
