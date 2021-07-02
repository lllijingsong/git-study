# github: https://github.com/lllijingsong/git.git
##生成SSH 密钥
`ssh-keygen -t rsa -c "873148577@qq.com"` 
在用户文件夹可以看到 `C:\Users\87314\.ssh`
此时不要关闭生成的命令窗口，使用
`cat /c/Users/87314/.ssh/id_rsa.pub` 可以查看刚刚生成的公共密钥

 git remote add origin http:// github .... // 绑定至远程

# git基本使用
 需要在github上创建账号, 需要在本机安装git软件, 并且配置于全局;

### 在本机配置git的基本信息:

    // config userName and userEmail // 查看配置信息;
    git config --global user.name 'llljingsong'
    git config --global user.email '873148577@qq.com'
    git config --list


### 初始化git仓库

    git init // 初始化一个文件夹作为git仓库;

### 查看git仓库状态

    git status // 必须有文件更新的情况下才有数据更新;

# git三个区域
    git 有三个区域, 分别控制各种情况;

### 工作区(color: red)
    1. 在修改该文件夹的内容后, 可以输入git status命令, 出现红色的颜色的文件名(用户刚刚修改的文件);
    2. 现在的状态就是工作区;

### 暂存区(color: green)

    2. 查看暂存区文件 git ls-files
    3. 出现红色文件名后可以通过, git add . 或者 git add 该文件名 进行提交至暂存区域
    4. 提交完毕后, 再次查看git status 该文件的名称变成绿色;

### 版本区
    5. 变成绿色后, 可以进行提交至版本区域, 通过 git commit -m 'message' // 提交至版本区域;
    6. 再次查看git status, 发现已经没有任务可以操作的文件;
    7. 可以通过git log 查看提交日志;

# git常用的命令
### git clone http://xxxxx.git
    从远处代码库克隆代码到本地
### git status
    查看当前代码的转态
### git add .
    把工作区所有的代码传到暂存区
### git commit -a -m 'all code update' 
    -a是代表add，把所有的change加到git index里然后再commit

### git commit -m 'commit code'
    提交代码到版本区

### git push
    把代码提交到服务器

### git pull
    从服务器拉代码

### git diff
    作用: 查看当前工作区和暂存区代码的区别;
    首先, git add . 把代码上传到暂存区, 在这个操作之后如果又对该文件进行了修改, 就可以使用 git diff 命令查看修改的代码
    简称: 比较工作区和暂存区差异;

### git diff --cached
    作用: 查看比较暂存区和版本库的区别;
    简单说就是, 通过这个命令可以查看 暂存区的代码和版本库的代码区别并打印出来;

### git diff master
    作用: 查看工作区和版本库的差异;

###  git reset --hard HEAD^
	回退一个版本，删除上一次提交的内容，删除日志。
	`可以通过 git reflog 可以查看到这个日志`

### git reset --hard a82c0d8 回流至某一个版本
    git reset --hard a82c0d8, 将代码回退至某个时段;
    日志编码, 可以全部选择, 也可以只选择前7位;
    // 可以使用 git reflog 看更多的日志;

# git分支

### git branch
    查看当前git下的所有分支;

### git branch testing
    在当前的git上创建一条testing的分支;

### git checkout testing
    切换testing分支