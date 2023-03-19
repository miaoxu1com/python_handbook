批处理运行的时候最好申请下管理员权限在执行相关的代码否则会出现各种问题
任务栏会闪一下
@echo off
if "%1"=="h" goto begin
cd /d %~dp0
start mshta vbscript:createobject("wscript.shell").run("""%~nx0"" h",0)(window.close)&&exit
start %1 mshta vbscript:CreateObject("Shell.Application").ShellExecute("cmd.exe","/c %~s0 ::","","runas",1)(window.close)&&exit
:begin
taskkill /F /IM alist.exe 2>nul
start /b D:\alist-windows-amd64\alist.exe server
start http://127.0.0.1:5244

完美隐藏cmd
Set obj = CreateObject("WScript.Shell")

Dim kill_alist
Dim start_alist
Dim open_browser

kill_alist = "cmd /c start taskkill /F /IM alist.exe 2>nul"
start_alist = "cmd /c start /b /w D:\alist-windows-amd64\alist.exe server 2>nul"
open_browser = "cmd /c start http://127.0.0.1:5244"

obj.Run start_alist ,0
obj.Run open_browser,0
