### git学习笔记：

#### 1、生成ssh密钥对
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
把your_email@example.com替换成你在 Git 服务提供商处注册所用的邮箱。执行此命令后，会生成一个私钥文件（默认是~/.ssh/id_rsa）和一个公钥文件（默认是~/.ssh/id_rsa.pub）。

#### 2、添加私钥到 SSH 代理（加密）
先开启ssh代理，然后把私钥添加到ssh代理：

        ssh-add ~/.ssh/id_rsa

#### 3 、gitlab或者github配置公钥（解密）

#### 4、测试ssh连接
        ssh -vT git@github.com
如果控制台输出存在dns域名解析错误问题（ssh: connect to host github.com port 22: Connection refused），需要手动指定github.com的host；

#### 5、git提交代码流程
    # 初始化仓库
    git init
    
    # 添加所有文件到暂存区
    git add .
    
    # 查看暂存区状态
    git status
    
    # 配置提交身份信息（邮箱和用户名）
    git config --global user.name "Your Name"
    git config --global user.email "you@example.com"

    # 提交暂存区的变更到本地仓库
    git commit -m "初始提交"

    
    # 关联远程仓库（如果是clone的代码不用执行这段代码，已经默认关联了）
    git remote add origin git@github.com:username/repo.git
    
    # 拉取远程仓库的最新代码
    git pull origin main
    
    # 推送本地代码到远程仓库
    git push origin main
