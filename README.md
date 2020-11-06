# 					 *git与github微型指南*![](https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png)

首先创建一个[github账号](https://github.com/)，并下载好[git客户端](https://git-scm.com/downloads)。注册登录账号之后你得到了一个名为github.com/YourUserName的账号，在该页面点击Repositories（储存库），然后在右侧界面点击一个绿色的按钮New跳转到创建新项目页面。都是些很简单的英文，而且使用谷歌浏览器可以在需要翻译的页面下鼠标点击，选择翻译成简体中文。在创建新项目页面下的Repositoryname输入框写下你的项目名称，Description可写可不写，默认为公有目录（public），然后点击Create Repository创建项目就完成了。如果你是按我的教程步骤来运行的话就是这样，其实也可以添加自述文件和许可证，不过这样的话你在本地初始化应用后要先拉取。

1.初始化应用

```
git init（打开你的命令行窗口，在你的项目目录下运行该命令。）
```

2.提交文件（该命令将文件提交到本地暂存区，尚未提交到远程项目。）

```
git add  file（你的文件名，比如test.txt。提交全部文件使用 . ）
```

3.提交注释与查看提交历史

```
git commit -m "notes"（比如 git commit -m "This is first commit"）
git log（查看所有提交历史，该命令加上 -1 为查看上一次提交的历史。）
```

4.创建分支（2020年10月之前master是github的主分支名，现在默认为main）

```
git branch -m main（创建名为main的本地分支） 
git checkout -b test origin/main（在main分支的基础上创建名为test的新分支）
```

4.添加远程仓库（你的github项目链接）

```
git remote add origin "your project address"（比如 git remote add origin https://github.com/Test/test.git 。第一个Test是你的github用户名，第二个test是你的项目名称。进行该步骤时需先在github上创建项目。）
```

5.确认提交

```
git push -u origin main（main是你的项目主分支名，你可以创建新的分支并使用它的名字。仅在首次提交时需要使用 -u ，之后的提交使用 git push origin "your branch name"）
```

到这你就完成了第一个github项目的创建与提交，别人就可以在网上看见你提交的内容。在这里我默认你创建的是公有项目（public）。

6.查看状态

```
git status（任何时候当你想知道当前项目文件的状态时就可以使用这个命令，比如在将文件提交到暂存区时查看，提交到远程分支时再查看一次。）
```

7.取回命令

```
git fetch （该命令将把你的本地储存库文件状态更新为你github上项目的文件状态，更新特定分支使用 git fetch origin "your branch"）
```

8.查看分支与切换分支

```
git branch -a（查看本地所有分支，-r means remote）
git branch -r（查看远程所有分支，-a means all）
git checkout "your branch"（切换到指定分支，比如 git checkout main） 
```

9.展示工作区与暂存区的差异

```
git diff（该命令可以帮你更好的分析两者间的差异，按下q键退出查看。）
```

10.删除分支

```
git branch -d "your branch"（删除本地分支。）
git push origin --delete "your branch"（删除远程分支，如果没有授权只能删除自己的远程分支。）
```

11.删除文件

```
git rm "FileName"（如果要删除的文件已经提交到暂存区，在命令中添加 -f ，删除后记得提交到远程仓库。）
```

12.拉取合并

```
git pull origin "branch name"（该命令拉取远程分支到本地并合并到当前分支，比如当前分支是test，运行 git pull origin main 等于把远程main分支拉取到本地与test分支合并。）
git fetch "branch name" 与 git merge "branch name"（该命令等于手动合并，拉取后通过 git diff "branch name" 命令查看差异，根据需求合并。）
```

13.克隆项目

```
git clone "project address"（比如 git clone https://github.com/Test/test.git 。该命令将把名为test的项目克隆到你的本地目录，去clone任何你喜欢的项目吧。）
```

这个微型指南到这就结束了，好好享受吧，Good lucky!