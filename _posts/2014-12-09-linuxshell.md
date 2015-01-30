---
layout: post
title: vim,shell学习
category: 技术
tags: linux
---
#vim编辑器
##vim常用快捷键
[参考文件](http://www.cnblogs.com/gunl/archive/2011/08/15/2139588.html)
<table border="1">
  <caption>1.查找</caption>
    <tr>
    <th>/xxx</th>
    <td>表示在整篇文档中搜索匹配xxx的字符串, / 表示向下查找, ? 表示
                      向上查找.其中xxx可以是正规表达式,关于正规式就不多说了.
		                        一般来说是区分大小写的, 要想不区分大小写, 那得先输入
					                  :set ignorecase
							                    查找到以后, 再输入 n 查找下一个匹配处, 输入 N 反方向查找.</td>
    </tr>
    <tr>
    <th>*(#)</th>
    <td>当光标停留在某个单词上时, 输入这条命令表示查找与该单词匹配的
                      下(上)一个单词. 同样, 再输入 n 查找下一个匹配处, 输入 N 反方
		                        向查找.</td>
    </tr>
    <tr>
    <th>g*</th>
    <td>此命令与上条命令相似, 只不过它不完全匹配光标所在处的单词, 而
                      是匹配包含该单词的所有字符串.</td>
    </tr>
    <tr>
    <th>gd</th>
    <td> 本命令查找与光标所在单词相匹配的单词, 并将光标停留在文档的非
                      注释段中第一次出现这个单词的地方.</td>
    </tr>
    <tr>
    <th>%</th>
    <td>本命令查找与光标所在处相匹配的反括号, 包括 () [] {}</td>
    </tr>
    <tr>
    <th>f(F)x</th>
    <td>本命令表示在光标所在行进行查找, 查找光标右(左)方第一个x字符.
                      找到后:
		                        输入 ; 表示继续往下找
					                  输入 , 表示反方向查找
							  </td>
    </tr>
    </table>
<table border="1">
    <caption>2.快速移动光标</caption>
    <tr>
    <th>w(e)</th>
    <td>移动光标到下一个单词</td>
    </tr>
    <tr>
    <th>b</th>
    <td>移动光标到上一哥单词</td>
    </tr>
    <tr>
    <th>0</th>
    <td>移动光标到本行开头</td>
    </tr>
    <tr>
    <th>$</th>
    <td>移动到本行结尾处</td>
    </tr>
    <tr>
    <th>H</th>
    <td>移动到屏幕首行</td>
    </tr>
    <tr>
    <th>M</th>
    <td>移动到屏幕中间一行</td>
    </tr>
    <tr>
    <th>L</th>
    <td>移动到屏幕尾行</td>
    </tr>
    <tr>
    <th>gg</th>
    <td>移动到文档首行</td>
    </tr>
    <tr>
    <th>G</th>
    <td>移动到文档末尾</td>
    </tr>
    <tr>
    <th>c-f</th>
    <td>page down</td>
    </tr>
    <tr>
    <th>c-b</th>
    <td>page up</td>
    </tr>
    <tr>
    <th>''</th>
    <td>返回上一次标记处</td>
    </tr>
    <tr>
    <th>'.</th>
    <td>返回上一次修改行</td>
    </tr>
    <tr>
    <th>`.</th>
    <td>返回上一次修改点</td>
    </tr>
    </table>
<table border="1">
<caption>3.拷贝，删除，粘帖</caption>
    <tr>
    <th>yw</th>
    <td>复制到单词词尾</td>
    </tr>
    <tr>
    <th>dw</th>
    <td>删除到单词词尾</td>
    </tr>
    <tr>
    <th>y0</th>
    <td>复制到行首</td>
    </tr>
    <tr>
    <th>d0</th>
    <td>删除到行首</td>
    </tr>
    <tr>
    <th>y$</th>
    <td>复制到行尾</td>
    </tr>
    <tr>
    <th>d$</th>
    <td>删除到行尾</td>
    </tr>
    <tr>
    <th>yfa</th>
    <td>复制到第一个a</td>
    </tr>
    <tr>
    <th>dfa</th>
    <td>删除到第一个a</td>
    </tr>
    <tr>
    <th>yy</th>
    <td>复制光标所在行</td>
    </tr>
    <tr>
    <th>D</th>
    <td>删除到行尾</td>
    </tr>
<table border="1">
<caption>数字与命令</caption>
    <tr>
    <th>5fx</th>
    <td>查找第5个x</td>
    </tr>
    <tr>
    <th>5w</th>
    <td>移动到下5个单词</td>
    </tr>
    <tr>
    <th>5yy</th>
    <td>复制以下五行</td>
    </tr>
    <tr>
    <th>5dd</th>
    <td>删除以下5行</td>
    </tr>
    <tr>
    <th>y5fx</th>
    <td>复制到第5个x</td>
    </tr>
    <tr>
    <th>:12,24y</th>
    <td>复制12行至24行内容</td>
    </tr>
    <tr>
    <th>:12,y</th>
    <td>复制12行至光标所在行内容</td>
    </tr>
    <tr>
    <th>:,12y</th>
    <td>复制光标行至12行内容</td>
    </tr>
<table border="1">
<caption>5.快速输入字符</caption>
    <tr>
    <th>c-p(c-n)</th>
    <td>vim文档搜索匹配</td>
    </tr>
    <tr>
    <th>c-x-l</th>
    <td>本窗口整行内容补齐</td>
    </tr>
    <tr>
    <th>c-x-f</th>
    <td>补齐文件名</td>
    </tr>
   <tr>
    <th>abbr</th>
    <td> 即缩写. 这是一个宏操作, 可以在编辑模式中用一个缩写代替另一个
                      字符串. 比如编写java文件的常常输入 System.out.println, 这很
		                        是麻烦, 所以应该用缩写来减少敲字. 可以这么做:
					                  :abbr sprt System.out.println
							                    以后在输入sprt后再输入其他非字母符号, 它就会自动扩展为System.
									                      out.println</td>
    </tr>
</table>
<table border="1">
<caption>6.替换</caption>
    <tr>
    <th></th>
    <td></td>
    </tr>
   <tr>
    <th></th>
    <td></td>
    </tr>
    <tr>
    <th></th>
    <td></td>
    </tr>
   <tr>
    <th></th>
    <td></td>
    </tr>
    <tr>
    <th></th>
    <td></td>
    </tr>
   <tr>
    <th></th>
    <td></td>
    </tr>
    <tr>
    <th></th>
    <td></td>
    </tr>
   <tr>
    <th></th>
    <td></td>
    </tr>
    <tr>
    <th></th>
    <td></td>
    </tr>
</table>
##vim配置
#shell inout stream
##echo
finding bug
## >,2>,&>
## | redirecting and piping
## <<EOF create here document
```
grep -i $* <<EOF
#以后会学
name 123-4567
name1 123-5678
name2 123-6789
EOF

## running and commenting	 

```
chmod a+x file
bash -n file : checks syntax 
bash -v file : echos every line read
bash -x file : echos every line executed, no comments
# ： comments 
#! /bin/bash : tell the OS where to find bash

## &&,|| join 2 command together
&& : proceed only succeeded
|| : proceed only failed
## {} group the command
## if...fi
```
if {ll ; cd /tmp 2>./error}
then echo cd worked
else 
	echo cd failed
	exit 1
fi
echo continue...
exit 0

## shell variables : for parameters and command choosing
visible only in current file
## export : shell variables available between shells
## special variables
<tabel border="1">
<caption>special variables</caption>
<tr>
<th>PS1</th>
<td></td>
</tr>
<tr>
<th>PATH</th>
<td>using type command to check the type of command.PATH="$PATH:~/bin"</td>
</tr>
<tr>
<th>HOME</th>
<td>~</td>
</tr>
</tabel>
## printf : formating output

```
VAR=123
printf "my value is %d\n" $VAR
printf "VARhex=%#x\n" $VAR
printf "VARfloat=%6.3f\n" $VAR

## positional parameters

```
# new copy
SRC = "$0"
DEST = " $1" 
cp "$SRC" "$DEST"

```
chmod a+x myscript
./myscript /tmp ./

## $*,$#,$@ : shell notation : all params	
$# : number of params

$* : 

$@ : 

## %,#,/ : changing values with simple substitution

```
host:path

FULL=${1}
FN=${FULL#*:}
HOST=${FULL%:*}
echo HOST is $HOST
echo PATH is $FN
FILE= '01 track 01.mp3.mp3'
echo ${FILE} ${FN/ track ??.mp3}


```
bash myscript.sh hostname:/dir/dir2/file




