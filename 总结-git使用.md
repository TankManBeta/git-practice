# 提交项目至GitHub仓库

1. 新建仓库，会出现仓库地址，例如：https://github.com/TankManBeta/git-practice.git

2. 本地项目文件夹，打开根目录命令行窗口，输入以下命令：

   ```shell
   git init
   git add .
   git commit -m "first commit"
   git branch -M main #-M 参数是用来分支改名的
   git remote add origin https://github.com/TankManBeta/git-practice.git
   git push -u origin main
   ```

3. 本地项目上传至GitHub仓库成功

# Tips

## 每次上传需要登陆

git使用https协议，每次pull, push都要输入密码。使用git协议，然后使用SSH密钥，可以不用每次都输密码。

1. 生成SSH

   1. 打开Git，输入：

      ```shell
      ssh-keygen
      ```

   2. 设定保存key的文件名

   3. 设定密码

2. GitHub主页添加SSH： Settings --> SSH and GPG keys --> New SSH key --> 输入自定义标题和刚刚生成的pub文件 --> Add SSH key

3. 本地登陆SSH

   1. Git输入命令：

      ```shell
      ssh -T git@github.com
      ```

4. 移除旧的提交方式：

   1. 查看项目采用的提交方式：

      ```shell
      git remote rm origin
      ```

   2. 修改提交方式

      1. GitHub仓库 --> Clone or download --> User SSH，获取SSH链接

      2. 添加新的SSH提交方式

         ```shell
         git remote add origin git@github.com:TankManBeta/git-practice.git
         ```

5. 提交项目，不再需要输入账号密码