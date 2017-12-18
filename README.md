# person
前端测试服务器：
服务器：192.168.1.185
用户/password：root/123456

进入xshell后定位到工时项目命令：
cd workspace/tm_timesheet/

获取最新源码:
git pull
(注：获取失败的情况下，可以还原当前本地最新版本
git reset --hard origin/master，之后再git pull)

代码部署：
npm run pre

服务重启：
先通过pm2 list 命令查看项目列表
pm2 restart appname （注：0对应项目列表的id）
