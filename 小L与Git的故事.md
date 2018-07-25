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

等做完这一切后, 小L想看一下仓库是否有妥善地保存这个箱子: 

git log

但他觉得每次都把箱子打开看各种参数很麻烦, 他只需要知道箱子编号和备注就好了, 于是:

git log --pretty=oneline

但小L似乎感觉改动的部分越改越差了, 他想返回上一个版本去重新查看之前的内容:

git reset --hard HEAD^

然后发现这个版本里没找到之前的改动, 于是通过git log 找到之前第n个版本的版本号前几位: 1094a

git reset --hard 1094a

发现这个改动确实没错, 于是维持更改, 但他现在想回到最新的版本: 

git reflog
git reset --hard 最新版本的版本号前几位

小L这下想即时查看上一个版本和当前修改后还没提交的版本两者之间的改动的区别:

git diff HEAD -- novel.txt

小L有时把增加的内容放进"箱子"(暂存区)后觉得不满意又拿了出来删掉了:

git checkout -- novel.txt

但有时候小L是把内容增加进箱子并且已经提交了, 这时候他想删除该怎么办呢?

是的, 只能将版本倒退, 或者提交新版本时删除, 还好此时这些操作都发生在小L自己的电脑上. 一旦上传到网站, 那就没法更改了..

第二天, 小L想删除文件夹里的大纲.txt的文件

git rm novel.txt

正如上面看到的, 小L误删了小说的文件, 这时可把他急坏了, 还好我们又"一键还原"命令:

git checkout -- novel.txt

现在, 小L将写好的第一章内容修改润色了一遍, 准备上传到网站上供读者阅读

首先, 他要将自己电脑和网站的个人账户连接起来

git remote add origin git@github.com:xiaoL/novel.git














