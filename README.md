# TongjiCoursesClock

## 使用方式
### 安装TamperMonkey
Tampermonkey 是一款免费的浏览器扩展和最为流行的用户脚本管理器,它适用于 Chrome, Microsoft Edge, Safari, Opera Next, 和 Firefox。相关安装方式参照互联网即可。
### 安装脚本
访问https://greasyfork.org/zh-CN/scripts/397174-tongji-courses-clock ，选择安装此脚本。安装脚本的源代码在安装页面是开源的。

## 使用说明
登录courses.tongji.edu.cn，确保用户脚本运行后，将页面挂在后台。无论是PC还是手机浏览器，理论上只要保持这个页面运行就可以发送通知。
在课程开始时间五分钟前，courses.tongji.edu.cn会发送桌面通知提醒即将开始的课程、教师以及会议号和密码。
会议号和密码是在登录时获得的，请以上课前平台上实际的会议号和密码为准。

## 如何确保用户脚本运行情况
chrome等PC浏览器在页面按F12，手机浏览器使用其他方式进入开发者模式。如果控制台上有来自userscript的Array()等输出，则脚本正常运行。

## 关于
脚本是基于个人懒人需求以及练习js目的而产生，主要是解决个人看视频、玩游戏导致的迟到问题，个人又是沉迷PC用户懒于设置手机日程，因此使用桌面通知提醒我上课。实际使用价值并不大~
脚本还没经过严谨测试，可能出现大量有的没的问题~
如果有大佬有办法做成web-push式的后台非访问推送通知，希望不吝赐教QAQ。
脚本基于用户登录后产生的cookies中的用户信息调用学校接口获取课程信息，目前设置为获取登录时间起7天的课程，不会将信息存入其他数据库，仅在用户浏览器本地使用。
脚本页面为私链，仅能通过url访问，无法在greasy fork中搜索到。

## 5分钟太久怎么办
点击TamperMonkey扩展图标，选择管理面板，右键点击Tongji Courses Clock编辑代码。在第54行

`
if(new Date(item.start).getTime() - new Date().getTime() <= 300000 && new Date(item.start).getTime() - new Date().getTime() > 240000)
`

这一行代码的300000毫秒和240000毫秒对应的是5分钟和4分钟，比如想设置成提前2分钟就改成120000和60000。

## 联系作者
QQ：461304186或者发邮件至QQ邮箱。
