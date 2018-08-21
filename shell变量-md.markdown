# 变量
## &emsp;变量的可变性与方便性
* 账号邮件信箱默认以mail这个变量进行访问。当用户dmtsai登录，他便会取得MAIL这个变量，而这个变量内容其实是/var/spool/mail/dmtsai。如果vbird登录，则MAIL变量的内容就是/var/spool/mail/vbird。
* 而我们使用命令mail读取邮箱时，这个程序可以直接读取mail这个变量的内容，就能够自动分辨出属于自己的信箱了。
* 注意：MAIL是变量名称，mail是命令。
* mail命令通过MAIL变量进行读取。
## 影响bash环境操作的变量
### 环境变量
* PATH罗列出shell搜索用户输入的命令所在的目录。
* HOME（LUNIX）和userprofile（Microsoft Windows）表示用户的主目录在文件系统中的位置。
* TERM (类Unix系统) 指定使用终端或虚拟终端 的类型 (如, vt100 or dumb)。
* CVS_RSH (类Unix系统) 该选项可用于 ext 方式中指明 cvs 客户端寻找远端 shell 的路径，用作连接 cvs 服务器和以更高的优先权覆盖 $CVS_RSH 环境变量中指定的路径。
* MAIL (类Unix系统) 当前用户的邮件存放目录。
## shell script的好帮手
* 编写较为大型的shell script时，可以在script最前面定义某变量表示什么内容，当需要进行修改时，只需要修改变量即可。
* * * * * * *
# 变量的显示与设置：echo，unset
## &emsp;变量的显示echo
* 示例：
	#echo $variable
	#echo $PATH
	#echo ${PATH}
* 利用echo可以读出变量内容，方法如上示例。其他功能，man echo
## 变量的设置规则
1.变量与变量内容以“=”连接，如示：    
   * myname=VBird     

2.等号两边不能直接接空格符      

3.变量名称只能是英文字母与数字，但*开头字符不能为数字*       

4.变量内容若有空格符,可以使用双引号“"”或者单引号”'“将变量内容结合起来    
   * 双引号内特殊字符如$等可以保有原本的特性，如下所示:    
   若"var="lang is $LANG""，则"echo $var"可得"lang is en_US"    
   * 单引号内的特殊字符则仅为纯文本，如下所示：        
   若"var='lang is $LANG'"，则"echo $var"可得"lang is '$LANG"        

5.可以用*转义字符"\"*将特殊字符（如ENTER、$、\、空格符、！等）变成一般字符    

6.在一串命令中还需要通过其他的命令提供的信息，可以使用反单引号`（数字1左边的那个按键）“`命令`”或“$（命令）”。例如：    
   * “version=$(uname-r)"再"echo $version"可得“内核版本号”     

7.若该变量为了增加变量内容，则可用"$变量名称"累加内容，如示：     
* "PATH="$PATH":/home/bin"      

8.若该变量需要在其他子进程执行，则需要export来使变量变成环境变量：    
* "export PATH"                                                   

9.通常大写字符为系统默认变量，自行设置变量可以使用小写字符，方便判断     

10.取消变量的方法为使用"unset 变量名称"，例如取消myname的设置：     
   * "unset mtname"
