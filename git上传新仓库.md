#### git

1. 建立ssh连接

2. git init

3. git status

4. git add .

5. git commit -m ‘ 。。。。。。。。。。’

6. git remote add origin https://github.com/oykaiwyh/vue.git             //增加一个远程分支与github仓库地址关联

7. git push -u origin master     //推送代码（第一次加-u，之后不用）出错执行第八

8. 另外，这里有个坑需要注意一下，就是在上面第七步创建远程仓库的时候，如果你勾选了Initialize this repository with a README（就是创建仓库的时候自动给你创建一个README文件），那么到了第九步你将本地仓库内容推送到远程仓库的时候就会报一个failed to push some refs to  https://github.com/guyibang/TEST2.git的错。

   ​      ![img](https://img-blog.csdn.net/20170414212947320)

   ​      这是由于你新创建的那个仓库里面的README文件不在本地仓库目录中，这时我们可以通过以下命令先将内容合并以下：

   

   ```
   $ git pull --rebase origin master
   ```

   ​       ![img](https://img-blog.csdn.net/20170414213315899)



#### 命令

1. git remote add origin
2. git remote rm orogin   //删除远程分支---增加远程分支地址出错时
3. 