资源管理器中双击文件夹/目录时使用的默认打开程序 ，使用官方TC win+e打开实例后双击文件夹 会直接使用已打开的实例

Windows Registry Editor Version 5.00
控制双击磁盘根目录时的打开行为,如C:\、D:\ 等盘符目录。
[HKEY_CLASSES_ROOT\Directory\shell\open\command]
@="\"d:\\totalcmd\\TOTALCMD64.EXE\" /O /L=%1
控制双击普通文件夹时的打开行为
HKEY_CLASSES_ROOT\Folder\shell\open\command
@=\"D:\TotalCommander\TOTALCMD.EXE\" /O /L=%1

HKEY_CLASSES_ROOT\Directory的设置优先级更高。
如果HKEY_CLASSES_ROOT\Folder未设置,会回退到HKEY_CLASSES_ROOT\Directory的设置。
对于磁盘根目录,会优先使用HKEY_CLASSES_ROOT\Directory的设置。
对于普通文件夹,没有设置时会使用HKEY_CLASSES_ROOT\Directory的默认值。
所以简单来说,这两个键的值最好保持一致,以避免双击不同文件夹出现不一样的行为。
常见的做法是同时设置这两个键值指向外部程序,如Total Commander,以实现双击任何文件夹都用该程序打开。


HKEY_CLASSES_ROOT\Folder\shell\opennewprocess是一个Registry键,它用于控制在Windows资源管理器中双击文件夹时是否使用新进程打开。

其默认值为空,表示双击文件夹时直接使用默认的打开程序打开,不启动新进程。

如果将其设置为一个字符串值,那么双击文件夹时就会启动一个新进程来打开文件夹,而不是重用已运行的程序实例。

举个例子:

如果默认的文件夹打开程序是Total Commander,正常双击会重用已经启动的Total Commander来打开文件夹。

但如果设置HKEY_CLASSES_ROOT\Folder\shell\opennewprocess的值为任意字符串,那么双击时就会启用一个新的Total Commander进程。

这对于某些需要单独沙盒进程的程序来说很有用。

同样的,针对具体文件类型,也可以设置:

HKEY_CLASSES_ROOT.txt\shell\opennewprocess
HKEY_CLASSES_ROOT.jpg\shell\opennewprocess

来控制文件是否使用新进程打开。

需要注意,修改注册表后需要重新启动资源管理器进程或者注销登录才会生效。

HKEY_CLASSES_ROOT\Folder\shell\opennewwindow是一个Registry键值,它用于控制在Windows资源管理器中双击文件夹时,是否使用新窗口打开文件夹。

其默认值为空,表示双击时直接调用默认程序打开文件夹,不会打开新窗口。

如果设置该键值为一个字符串,那么双击文件夹时,会强制使用一个新的程序窗口来打开文件夹,而不是重用已有窗口。

例如,如果默认程序是资源管理器Explorer.exe,双击文件夹正常情况下会在已打开的资源管理器窗口中打开。

但设置了HKEY_CLASSES_ROOT\Folder\shell\opennewwindow后,双击时会重新打开一个新的资源管理器窗口。

这对某些需要单独窗口的场景比较有用。

类似的,针对具体文件类型,也可以设置:

HKEY_CLASSES_ROOT.txt\shell\opennewwindow
HKEY_CLASSES_ROOT.jpg\shell\opennewwindow

来控制该文件类型是否使用新窗口打开。

需要注意,修改注册表后需要重启资源管理器或注销登录才会完全生效。

HKEY_CLASSES_ROOT\Folder\shell\open键值用于控制在Windows资源管理器中双击文件夹时的默认打开行为。

其中的子键包含了几个重要的设置:

command - 默认值,表示双击文件夹时调用的程序路径,默认为explorer.exe
ddeexec - 设置DDE执行命令,可以通过DDE控制打开行为
opennewprocess - 设置为1表示使用新进程打开文件夹
opennewwindow - 设置为1表示使用新窗口打开文件夹
Droptarget - 设置文件夹的拖放相关行为
常见的修改是将command键值设为其他文件管理器的路径,如Total Commander,这样双击时就会用它来打开文件夹了。

另外,可以通过设置opennewprocess和opennewwindow来控制单独的进程和窗口打开。

修改后需要重启资源管理器才能完全生效。

类似的注册表键还有:

HKEY_CLASSES_ROOT\Directory\shell\open
控制双击目录的行为。

HKEY_CLASSES_ROOT.txt\shell\open
HKEY_CLASSES_ROOT.jpg\shell\open
控制指定文件类型的打开行为。

这些注册表键可以让我们自定义双击打开文件的默认行为。


HKEY_CLASSES_ROOT\Folder\shell\explore键值用于控制在Windows资源管理器中右键文件夹时“在资源管理器中查看”的行为。

默认情况下,右键文件夹选择“在资源管理器中查看”会在当前资源管理器窗口打开该文件夹。

修改HKEY_CLASSES_ROOT\Folder\shell\explore键值可以改变这一行为。

常见的修改包括:

设置command子键值为新资源管理器进程的路径,以使用新实例打开文件夹。
设置command子键值为其他文件管理器的路径,以使用第三方工具打开。
设置opennewwindow子键值为1,强制使用新窗口打开。
设置opennewprocess子键值为1,强制使用新进程打开。
例如,设置command为 totalcmd.exe,就会用Total Commander打开文件夹了。

类似的键还有:

HKEY_CLASSES_ROOT\Directory\shell\explore
控制目录的“在资源管理器中查看”行为。

通过修改这些注册表键,可以自定义在资源管理器中浏览文件夹和目录的行为,自动打开到指定的工具或新窗口中。


在Windows资源管理器中右键文件夹时弹出的上下文菜单中的“打开”项对应的注册表键。

主要的注册表键如下:

对于文件夹,是:

HKEY_CLASSES_ROOT\Folder\shell\open\command

对于特定文件类型,如.txt文件,是:

HKEY_CLASSES_ROOT.txt\shell\open\command

对于磁盘目录,是:

HKEY_CLASSES_ROOT\Directory\shell\open\command

这些键值决定了右键点击后选择“打开”时的行为,默认调用的是Explorer.exe。

如果要修改默认的打开程序,可以把这些键值改成新的程序路径,并添加参数"%1"传递点击的文件/文件夹路径,例如:

"C:\Program Files\WinRAR\WinRAR.exe" "%1"

这样右键打开就会调用WinRAR了。

另外,这些键下也包含了一些其他相关设置:

opennewwindow - 设置是否在新窗口中打开
opennewprocess - 设置是否启用新进程打开
修改注册表后需要重启资源管理器生效。

所以通过调整这些注册表键可以自定义右键的“打开”行为。
