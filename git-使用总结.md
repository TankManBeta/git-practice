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

3. 本地项目上传至`GitHub`仓库成功

# Tips

## 每次上传需要登陆

`git`使用`https`协议，每次`pull`, `push`都要输入密码。使用`git`协议，然后使用`SSH`密钥，可以不用每次都输密码。

1. 生成`SSH`

   1. 打开`Git`，输入：

      ```shell
      ssh-keygen
      ```

   2. 设定保存`key`的文件名

   3. 设定密码

2. `GitHub`主页添加`SSH`： `Settings` --> `SSH and GPG keys` --> `New SSH key` --> 输入自定义标题和刚刚生成的pub文件 --> `Add SSH key`

3. 本地登陆`SSH`

   1. 添加`Key`到`ssh`

      ```shell
      ssh-add  ~/.ssh/id_rsa
      ```

      ```shell
      ssh-add  ~/.ssh/你的私钥名
      ```

   2. `Git`输入命令：

      ```shell
      ssh -T git@github.com
      ```

      ```shell
      ssh -T -i 你的私钥名 git@github.com
      ```

      **注：设置了自定义名字的SSH密钥后，还需要再设置一下`SSH`的配置文件（见另一篇），否则会导致拒绝连接。**

4. 移除旧的提交方式：

   1. 查看项目采用的提交方式：

      ```shell
      git remote -v
      ```

   2. 删除旧的提交方式：

      ```shell
      git remote rm origin
      ```

   3. 修改提交方式

      1. `GitHub`仓库 --> `Clone or download` --> `User SSH`，获取`SSH`链接

      2. 添加新的`SSH`提交方式

         ```shell
         git remote add origin git@github.com:TankManBeta/git-practice.git
         ```

5. 提交项目，不再需要输入账号密码