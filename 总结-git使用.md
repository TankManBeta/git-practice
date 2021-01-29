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

git使用https协议，每次pull, push都要输入密码。使用git协议，然后使用ssh密钥，可以不用每次都输密码。