##[PL/SQLdevelop工具的使用技巧](http://blog.csdn.net/nomousewch/article/details/8699583)：

####1.PL/SQL Developer记住登陆密码:
在使用PL/SQL Developer时，为了工作方便希望PL/SQL Developer记住登录Oracle的用户名和密码；
设置方法：PL/SQL Developer7.1.2 ->tools->Preferences->Oracle->Logon History，“Store history”是默认勾选的，  
勾上“Store with password”即可，重新登录在输入一次密码则记住了。

####2.执行单条SQL语句
在使用PL/SQL Developer的SQL Window时，按F8键，PL/SQL Developer默认是执行该窗口的所有SQL语句，需要设置为鼠标所在的那条SQL语句，即执行当前SQL语句；
设置方法：PL/SQL Developer7.1.2-->tools->Preferences-->Window types，勾上“AutoSelect Statement”即可。

####3.格式化SQL语句
在使用PL/SQL Developer的SQL Window时，有时候输入的SQL语句太长或太乱，希望能用比较通用的写法格式话一下，这样看起来会好看些，也好分析；
使用方法：选中需要格式化的SQL语句，然后点击工具栏的PL/SQLbeautifier按钮即可.

####4.选中行高亮：
Preferences-->User Interface-->Editor-->other-->Highlight edit line；

####5.双击即显示表数据
鼠标双击表或者视图时的默认响应实在让我感到失望，因为我最关心的是表结构和数据，但是双击后这两件事情都没有发生，也许默认响应是高手们需要的，但对我来说查看数据和表结构是最主要的，其他的我不关心。不过好的是这是可以设置的，你可以给鼠标双击和拖放绑定需要的事件，比如：双击编辑数据，拖放显示表结构，Yeah！
设置方法：菜单Tools --> Preferences --> Browser，在右侧，为不同的Object Type绑定双击和拖放操作。

####6.SQL语句字符全部大写
自认为这是个好习惯，信息系统的核心是数据库，系统出问题时最先要查的就是SQL语句，怎样在浩瀚的日志中快速找到那条SQL语句是件比较痛苦的事情。 SQL语句全部大写并不能彻底解决这一问题，但在一堆代码中间找一行全部大写的字符相对容易些，你的眼睛会感谢你。
设置方法：菜单Tools --> Preferences --> Editor --> Keyword Case --> Uppercase

####7.特殊Copy    
在SQL Window里写好的SQL语句通常需要放到Java或者别的语言内，就需要转成字符串并上加上相应的连字符，这一个事不需要再重复做了，在写好的SQL上点右键，使用特殊Copy即OK！
设置方法：鼠标右键 --> Special Copy

####8.代码自动补全设置
工具 --> 首选项  --> 用户界面（编辑器） --> Autoreplace --> enabled=true --> edit -->输入你要替换的关键字并保存。

####9.登录后默认自动选中My Objects  
默认情况下，PLSQL Developer登录后，Brower里会选择All objects，如果你登录的用户是dba，要展开tables目录，正常情况都需要Wait几秒钟，而选择My Objects后响应速率则是以毫秒计算的。
设置方法：
Tools菜单 --> Brower Filters，会打开Brower Folders的定单窗口，把“My Objects”设为默认即可。
Tools菜单－－Brower Folders，中把你经常点的几个目录（比如：Tables Views Seq Functions Procedures）移得靠上一点，并加上颜色区分，这样你的平均寻表时间会大大缩短，试试看。

####10.自定义快捷键   
PLSQL Developer里预留了很多键让用户自定义，这是件很Hight的事情。不像霸道的Word，基本上所有的键都已预定义了功能，修改起来很是头疼。 通常情况下，打开PLSQL Developer后，最经常干的事就是打开SQL Window和Command Window，就给这两个操作定义了快捷键，ALT+S和ALT+ C，这样拿鼠标点三下的事情只需要按一下键。
设置方法：菜单Tools --> Preferences --> Key Configuration

####11.查看执行计划
在使用PL/SQL Developer的SQL Window时，有时候输入的SQL语句执行的效率，分析下表结构，如何可以提高查询的效率，可以通过查看Oracle提供的执行计划；
使用方法：选中需要分析的SQL语句，然后点击工具栏的Explain plan按钮（即执行计划），或者直接按F5即可。

####12.调试存储过程
在使用PL/SQL Developer操作Oracle时，有时候调用某些存储过程，或者调试存储过程；
调用存储过程的方法：首先，在PL/SQL Developer左边的Browser中选择Procedures，查找需要调用的存储过程；然后，选中调试的存储过程，点击右键，选择Test，在弹出来的Test scrīpt窗口中，对于定义为in类型的参数，需要给该参数的Value输入值；最后点击上面的条数按钮：Start debugger或者按F9；最后点击：RUN或者Ctrl+R。

####13.自动替换
快捷输入SQL语句，例如输入s，按下空格，自动替换成SELECT；再例如，输入sf，按下空格，自动替换成SELECT * FROM，非常方便，节省了大量的时间去编写重复的SQL语句。
设置方法：菜单Tools --> Preferences --> Editor --> AutoReplace. --> Edit
下面定义了一些规则作为参考
s=SELECT
f=FROM
w=WHERE
o=ORDER BY
d=DELETE
sf=SELECT * FROM
df=DELETE FROM
sc=SELECT COUNT(*) FROM
