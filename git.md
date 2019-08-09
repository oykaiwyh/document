### git 提交代码

```
1、git clone https://github.com/oykaiwyh/test.git

2、git branch yy    //创建yy的本地分支

3、git checkout yy		//选中本地分支yy

4、git push origin yy           //以本地yy分支为准，创建yy的远程分支

5、对拉取的项目进行CRUD   

6、git status     //查看修改过的代码

7、git add .                  //添加所有的修改内容进入缓存区

8、git commit -m '修改注释'    //提交修改到仓库

9、git pull origin master	//拉取最新代码到本地yy分支上

10、git push --set-upstream origin yy   	//设置本地分支追踪远程分支yy，只使用一次，之后直接使用git push即可
```

### git本地命令合并仓库分支

```
//git 本地合并到主分支
1. git checkout master
2.git pull 					//拉取最新代码
2.git merge 子分支
3.git push origin  //合并到主分支
```

### git命令

```
1.git branch -r  						//查看远程分支
2.git pull origin master  				//拉取远程最新信息到本地分支
3.git branch							//查看本地分支
4.git checkout  'originname' 			//切换分支到‘originname’
5.git branch -r							//查看远程分支
6.git branch -d 'originname'			//删除本地分支'originname'，需切换到其它分支再删除
7.git status							//查看代码状态
8.git add . 							//提交修改的所有信息到缓存区
9.git commit -m '修改注释'				 //提交代码到git仓库
10.git push 							//提交代码到远程仓库
11.git pull								//拉取代码到本地
12.git push --set-upstream origin 'originname'				//将本地分支设为远程分支
13.git clone '项目http或者ssh链接'							//将远程代码拉取到本地
14.git remote origin 'originname' 							//删除远程分支
```

