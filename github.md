## 版本控制工具

- 理论

  - Git是什么?

  >Git 是一款分布式版本管理的软件,Linux 内核,通过命令行进行操作.
  >
  >Git是您在计算机上本地安装的一个软件，它为您处理“版本控制”

  - 什么是分布式?

  >Git 属于分布式版本控制系统，而 SVN 属于集中式。
  >
  >集中式:
  >
  >​	集中式版本控制只有中心服务器拥有一份代码,
  >
  >​	集中式版本控制有安全性问题，当中心服务器挂了所有人都没办法工作了。
  >
  >​	如果网速过慢，那么提交一个文件的会慢的无法让人忍受.
  >
  >​        而集中式版本控制新建一个分支相当于复制一份完整代码。
  >
  >分布式:
  >
  >​	分布式版本控制每个人的电脑上就有一份完整的代码,
  >
  >​	分布式版本控制不需要连网就能工作.
  >
  >​	分布式版本控制新建分支、合并分支操作速度非常快.	

  - 有什么作用?

  >它记录了我们每一次对项目的新增、修改，删除等操作。
  >
  >当你的项目出现BUG的时候,我直接可以定位我修改了哪些部分,从而进行直接修改.
  >
  >新发版本在服务器上出现问题,不要慌,我可以将服务器上的代码回退一个版本.
  >
  >试想一下Boos我要开发一个新功能,于是我开发了项目2.0,Boss一看觉得不行,这个功能很突兀放在这,还是要1.0那个版本好,OK,恢复1.0版本,3天后,小明啊,投资人,要看2.0版本那个新功能,你赶紧发一版.无惧

  - Git与gitHub是什么关系?

  >Git        相当与是本地库,在自己电脑上编辑
  >Github 相当与是远程库,代码都是有Git在本地修改进行上传.
  >
  >Github 是以个开源(MIT)代码托管仓库,但是内容是需要Git进行本地上传的.
  >
  >Gitlab  部署在服务器上面,功能跟 Github是一样,它可以创建免费的私有库
  >
  >从功能上看没有关系,但是从内容产出,又是相辅相成的.
>
  >Github代码都需要public(公开), 如果你想要创建private(私人)的repo, 那得付钱。

  

  start

- Git初始化配置

```base
//ssh密钥很坑
配置个人的用户名称和电子邮件地址,Git 每一次提交时都会引用这两条信息,说明是谁提交了更新,并记录历史.没有添加信息,不能给提交文件加log
$ git config --global user.name "注册名称"
$ git config --global user.email "注册邮箱@xxx"
git config --list 查看

2.将密码缓存到本地,缓存完毕之后,在进行提交还是要进行一次密码验证,缓存完毕
$ git config --global credential.helper store
```

- 文件提交操作

  ```banse
  //拷贝项目
  $ git clone  https://github.com/name/xxxx
  
  $ git status 红色代表,没有添加追踪
  
  $ git add <file>|| git add . 增加单个追踪或所用追踪
  
  $ git status 绿色代表,添加追踪
  
  // 注意:本地提交完毕,可以进行远程提交与合并分之添加日志,
  $ git commit -m "xxxxxxxxxxxxx"  //良好习惯 一定要有意义
    git status 
  $ git push    提交远程库   
  ```

- 分之操作(branch)

  - 基本操作

  ```banse
   $ git branch -r        //查看远程分之:
   $ git branch -v        //查看本地分之
   $ git branch -a        //查看所有分之
      	
   $ git branch <branch>       //创建本地分之
   $ git checkout -b <branch>  //创建分之并移动至创建的分之
   $ git checkout -b <branch> <origin/branch> //创建本地dev与远程dev分之
   $ git push origin <branch>  //提交远程分之
      	
   $ git branch -D <branchName>  //删除本地分之  	
   
   $ git push origin :dev   	   //删除远程分之
```
  
- 分之合并
  
  ```base
  //重要:
      //1.注意在一个工作区工作没有完成,不能进行合并(commit log标注完毕在执行合并任务)
      //2.合并分之  dev>master 你需要完成commit_log,并且移动master分之 之后在进行合并
  $ git clone
  $ git branch xxx
  //修改代码完毕,移动到需要合并的分之
  $ git checkout master
  $ git merge dev
  //将测试分之合并至 主分支
```
  
  

​	

  

  

  

  

  

  

  


