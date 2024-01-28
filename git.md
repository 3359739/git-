# git基本使用

git就是一个文件管理软件

例如：比如你平常在敲代码做项目的时候你项目上线你的第1个版本，然后开发第2版本，在开发中你的第一个版本出现了bug然后git但你在平常是不是要找个文件把你正在开发的代码存起来，而git可以帮你帮你只执行相关的命令就可以(简单来说就是存储你代码的发展过程记录你代码的更新要你随时可以回到之前的内容而且不删除现有的内容)

## git创建和提交仓库的基本流程

```js
//第一进入你要管理的文件夹
cd ....
//在根目录执行 下面代码
git init //意思是创建一个git仓库用来存放你的代码
```

```js
//查看当前目录要管理的状态红色为没有被管理或修改和新增
git status 
```

<img src="C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128172517928.png" alt="image-20240128172517928"  />

```js
//要是我们想管理起来需要进行
git add . //(.代表全部管理或后面.更换为其他文件)
```

```js
//上面执行的都是要我们管路起来 要是要进行保存我们需要进行提交到仓库
git commit -m 版本名(自定义)
```

![image-20240128173001602](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128173001602.png)

```js
//查看仓库的版本
git log
```

以上就是基础的把代码托管给了git



## git回滚

例如我们对上述代码1.py进行了更新或增加了功能

我们要进行 

```
git add . 修改后我们要对他进行重新的提交到管理
git commit -m 版本号 提交到仓库 
```

现在我们仓库就用俩个板本 版本1和版本2 我们现在所在的版本是2当我们想回到1版本的时候而不需要改动2版本的对象需要进行回滚

```
git reset --hard 版本号 就可以对其进行回滚
查看版本号 git log
```

![image-20240128173826985](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128173826985.png)

```
当我们进行归滚的时候我们在进行git log 是看不到第2板本的要是想查看之前版本2的版本号 
git reflog
```

![image-20240128174859436](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128174859436.png)

后执行回滚

```
git reset --hard 版本号
```



## git分支

什么是分支就我们上面的代码都是一条线分支，例我们上述的代码回滚到第1版本修改到码想在第2版本上显示是不行的我们可以创建另外一条线在那对版本1进行修改然后合并到版本2上

```
查看分支 git branch 刚开始我们的主支是master 出现绿色就表示您当前处在那个分支
```

![image-20240128181135947](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128181135947.png) 

```
创建分支 (他回有你之前的版本)
git branch 分支名称
```

```
切换分支
git checkout 分支名称
```

然后我们就可以进行修改版本1的内容修改完成后要切换回主分支就是master

```
git merge lxh
```

可以开多个分支出现冲突就进行删除冲突

# GitHub使用

git是保存在我们本地仓库GitHub就相当一个远程仓库例如：我们平常在家敲代码但是我们出去外面又要敲同一份代码这样我们平常要用u盘保存起来带来带去但是GitHub就相当u盘但他是网站u盘，我们只需要通过命令然后就可以进行把我们写的代码上传上去到另外一个地方在从这个网站拿下来 就是GitHub：https://github.com/

1. 创建仓库![image-20240128192906954](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128192906954.png)![image-20240128192926001](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128192926001.png)

2. 通过git连接是你创建的仓库

   ```
   git remote add origin (git给的网址)  这个意思是给你链接的网址取别名origin
   ```

   ![image-20240128193130544](C:\Users\林显豪\AppData\Roaming\Typora\typora-user-images\image-20240128193130544.png)

3. 把你的代码上传到仓库

   ```
   git push -u 上面origin别名 上传的分支
   ```

4. ```
   把代码从GitHub拿下来
   git pull 网址别名 分支名
   ```

   

   