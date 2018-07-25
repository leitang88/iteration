小L是一个健忘的网络写手, 他的工作就是把写好的文章上传到小说网站上去.

因此, 他需要一个工具, 能够帮他记录他对小说的增删改查等操作, 经朋友介绍, 他安装了Git:

sudo apt-get install git

git config --global user.name "xiaoL"

git config --global user.email "xiaoL@gmail.com"

ssh-key -C "xiaoL@gmail.com" -t rsa

一番操作之后, 小L想查看这个Git版本是否是最新的, 于是他找到了这样一个命令:

git --version

待确认无误后, 小L准备开始使用这个新工具了!



