# **Git 工作流程**
>>### 工作流程
>>>>>>######  克隆 Git 资源作为工作目录。
>>>>>>######  在克隆的资源上添加或修改文件。
>>>>>>######  如果其他人修改了，你可以更新资源。
>>>>>>######  在提交前查看修改。
>>>>>>######  提交修改。
>>>>>>######  在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

>>### 工作流程图
![liuchengtu](https://www.runoob.com/wp-content/uploads/2015/02/git-process.png)

# **Git 工作区、暂存区和版本库**
>>### 基本概念
>>>###### 我们先来理解下Git 工作区、暂存区和版本库概念
>>>>>>###### **工作区**：就是你在电脑里能看到的目录。
>>>>>>###### **暂存区**：英文叫stage, 或index。一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
 >>>>>>###### **版本库**：工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。
>>>###### 图展示了工作区、版本库中的暂存区和版本库之间的关系：
![guanxi](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)

# **Git 笔记**
>>>###### Git 的工作就是创建和保存你项目的快照及与之后的快照进行对比。
>## 获取与创建项目命令
>>### git inti
>>>>>>######  mkdir runoob&emsp;&emsp;//创建项目
>>>>>>######  cd runoob/&emsp;&emsp;//进入项目
>>>>>>######  git init&emsp;&emsp;//初始化目.Git 库
>>>>>>###### ls -a&emsp;&emsp;//查看所有文件（包括隐藏等）

>>### git clone
>>>###### 使用 git clone 拷贝一个 Git 仓库到本地，让自己能够查看该项目，或者进行修改。
>>>###### 如果你需要与他人合作一个项目，或者想要复制一个项目，看看代码，你就可以克隆那个项目。 执行命令：
>>>>>>###### git clone[url]
>>>###### [url]为你想要复制的项目，就可以了
>>>###### 例如我们克隆Github上的项目：
>>>>>>######  git clone git@github.com:schacon/simplegit.git
>>>###### 克隆完成后，在当前目录下会生成一个simplegit目录：

>## 基本快照
>>>###### Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。
>>### git add
>>>>>>######  touch README&emsp;&emsp;//添加文件
>>>>>>######  ls&emsp;&emsp;//查看文件
>>>>>>######  git git status -s&emsp;&emsp;//查看项目的当前状态 是否为??&emsp;A状态的意思是：以提交或者以加上缓存的文件&emsp;AM状态的意思是：
>>>>>>######  git add 文件名
>>>>>>###### vim 文件名&emsp;&emsp;//使用vim修改文件(然后在使用git status -s 查看项目状态，然后使用git add 将其添加到缓存中)
>>>>>>######  git add .&emsp;&emsp;//将文件添加到缓存
>>>>>>######  git status&emsp;&emsp;//查看提交之后的文件是否有修改（查看要提交更变的文件）
>>### git diff
>>>>>>######  git diff&emsp;&emsp;//尚未缓存的改动
>>>>>>######  git diff --cached&emsp;&emsp;//查看已缓存的改动
>>>>>>###### git diff HEAD&emsp;&emsp;//查看已缓存的与未缓存的所有改动
>>>>>>######  git diff --stat&emsp;&emsp;//显示摘要而非整个 diff

>>### git commit
>>>###### Git 为你的每一个提交都记录你的名字与电子邮箱地址，所以第一步需要配置用户名和邮箱地址。
>>>>>>######  git config --global user.name '你的name'&emsp;&emsp;//配置你的用户名
>>>>>>######  git config --global user.email 你的邮箱&emsp;&emsp;//配置你的邮箱
>>>>>>######  git commit -m '第一次版本提交'&emsp;&emsp;//使用 -m 选项以在命令行中提供提交注释
>>>>>>###### git commit -a&emsp;&emsp;//如果你觉得 git add 提交缓存的流程太过繁琐，Git 也允许你用 -a 选项跳过这一步。
>>>>>>###### git commit -am '修改你的文件'&emsp;&emsp;//修改文件
>>### git reset HEAD
>>>###### git reset HEAD 命令用于取消已缓存的内容。
>>>>>>###### git reset HEAD hello.php &emsp;&emsp;//取消文件的缓存
>>### git rm
>>>>>>###### git rm 文件名 &emsp;&emsp;//要从 Git 中移除某个文件，就必须要从已跟踪文件清单中移除，然后提交。
>>>>>>###### git rm -f 文件名&emsp;&emsp;//如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 -f
>>>>>>###### git rm --cached 文件名&emsp;&emsp;//如果把文件从暂存区域移除，但仍然希望保留在当前工作目录中，换句话说，仅是从跟踪清单中删除，使用 --cached 选项即可
>>>>>>###### git rm –r * &emsp;&emsp;//可以递归删除，即如果后面跟的是一个目录做为参数，则会递归删除整个目录中的所有子目录和文件：
>>### git mv
>>>>>>######  git add 文件名&emsp;&emsp;//把刚移除的 文件 添加回来
>>>>>>######  git mv 被删除后添加回来的文件名  新的名字 &emsp;&emsp;//然后对其重名 然后使用ls查询

# **Git 分支管理**
>>>>###### 几乎每一种版本控制系统都以某种形式支持分支。使用分支意味着你可以从开发主线上分离开来，然后在不影响主线的同时继续工作。
>>>###### 列出分支
>>>>>>###### git branch&emsp;&emsp;//列出分支基本命令
>>>>>>###### git branch&emsp;&emsp;//没有参数时，git branch 会列出你在本地的分支。(查询你的分支)
>>>>>>###### $ echo '输入的内容' > 将被输入内容的文件名&emsp;&emsp;//制定输入给莫个文件
>>>>>>###### git checkout testing(切换的分支)&emsp;&emsp;//切换到要修改的分支
>>>>>>###### git checkout master（切换的分支）&emsp;&emsp;//但是当我们切换到 testing 分支的时候，我们添加的新文件 test.txt 被移除了。切换回 master 分支的时候，它们有重新出现了。
>>>>>>###### git checkout -b newtest（分支名）&emsp;&emsp;//创建新分支并立即切换到该分支下，从而在该分支中操作。
>>### 删除分支
>>>>>>###### git branch -d 删除的分支名字&emsp;&emsp;//删除分支
>>### 分支合并
>>>>>>###### git merge 合并的分支名&emsp;&emsp;//合并分支
>>### 合并冲突
>>>>>>###### cat 文件名 &emsp;&emsp;//查看文件内容
>>>>>>##### 合并冲突需要手动去修改然后使用（git add 文件名 ）告诉Git文件冲突已经解决

# **Git 常看提交历史**
>>>>>>###### git log &emsp;&emsp;//查看提交的历史

# **Git 标签**
>>>>>>###### git tag -a v1.0 &emsp;&emsp;//给最新一次提交打上（HEAD）"v1.0"标签
>>>>>>###### git tag  &emsp;&emsp;//产看所有标签
>>>>>>###### git tag -a <tagname> -m "runoob.com标签"&emsp;&emsp;//指定标签信息
>>>>>>###### git tag -s <tagname> -m "runoob.com标签"&emsp;&emsp;//PGP签名标签

# **Git  远程仓库(Github)**
>>### 添加远程库
>>>>>>###### ssh-keygen -t rsa -C "你的邮箱"
>>>>>>>>##### 之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在 ~/ 下生成 .ssh 文件夹，进去，打开 id_rsa.pub，复制里面的 key。然后去Github 点击 SSH and GPG keys，然后点击 New SSH key 按钮,title 设置标题，可以随便填，粘贴在你电脑上生成的 key。
>>>>>>######  ssh -T git@github.com&emsp;&emsp;//查看是否验证成功如果出现Hi xxx(你的名子)! You've successfully authenticated, but GitHub does not provide shell access.说明已经连接上了Github
>>>>##### 根据 GitHub 的提示，在本地的仓库下操作步骤
>>>>>>###### mkdir runoob-git-test &emsp;&emsp;//创建测试目录
>>>>>>###### cd runoob-git-test/   &emsp;&emsp;
>>>>>>######    &emsp;&emsp;//进入测试目录
>>>>>>######  echo "# 菜鸟教程 Git 测试" >> README.md   &emsp;&emsp;//创建 README.md 文件并写入内容
>>>>>>######  ls     &emsp;&emsp;//查看目录下的文件
>>>>>>######  git init  &emsp;&emsp;//初始化
>>>>>>######   git add README.md    &emsp;&emsp;//添加文件
>>>>>>######   git remote add origin git@github.com:tianqixin/runoob-git-test.git &emsp;&emsp;//提交到 Github
>>>>>>######   git push -u origin master  &emsp;&emsp;
>>### 查看但前远程库
>>>>>>###### git remote &emsp;&emsp;//查看当前的远程库
>>>>>>###### git remote -v&emsp;&emsp;//执行时加上 -v 参数，你还可以看到每个别名的实际链接地址。
>>### 提取远程仓库
>>>>>>###### git fetch &emsp;&emsp; //从远程仓库下载新分支与数据
>>>>>>###### git merge &emsp;&emsp; //从远端仓库提取数据并尝试合并到当前分支
>>>>>>###### git fetch origin &emsp;&emsp;  //本地更新修改(以上信息"0205aab..febd8ed master -> origin/master" 说明 master 分支已被更新)
>>>>>>###### git merge origin/master&emsp;&emsp;//更新同步到本地（然后使用cat 文件名查看文件内容）
>>### 推送到远程仓库
>>>###### 推送你的新分支与数据到莫个远端仓库
>>>>>>######  git push origin master &emsp;&emsp;//推送到 Github
>>### 删除远程仓库
>>>>>>###### git remote rm 远程库名 &emsp;&emsp;//删除仓库

