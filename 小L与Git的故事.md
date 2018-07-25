小L是一个健忘的网络写手, 他的工作就是把写好的文章上传到小说网站上去.

因此, 他需要一个工具, 能够帮他记录他对小说的增删改查等操作, 经朋友介绍, 他安装了Git:

sudo apt-get install git

git config --global user.name "xiaoL"

git config --global user.email "xiaoL@gmail.com"

ssh-key -C "xiaoL@gmail.com" -t rsa

一番操作之后, 小L想查看这个Git版本是否是最新的, 于是他找到了这样一个命令:

git --version

待确认无误后, 小L准备开始使用这个新工具了!

小L首先找到了他写小说的文件夹, 在命令行中进入这个文件夹, 然后把这个文件夹设置为git仓库:

git init

此时生成了一个.git文件夹, 但小L并没有意识到, 因为是一个隐藏文件夹

小L新建了一个章节, 写了几百字, 准备保存记录, 他首先要做的是将改动添加到"箱子"里:

git add *

等不想继续装箱时, 就把这一箱子的改动都放进仓库, 并给这个箱子写上备注:

git commit -m "第一章第一节, 写了几百字, 不是太满意"

等昨晚这一切后, 小L想看一下仓库是否有妥善地保存这个箱子: 

git log

但他觉得每次都把箱子打开看各种参数很麻烦, 他只需要知道箱子编号和备注就好了, 于是:

git log --pretty=oneline


