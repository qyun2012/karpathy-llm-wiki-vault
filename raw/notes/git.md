# 1. 添加远程仓库
git remote add origin (https://github.com/repos?q=owner%3A%40me)

# 2. 配置用户信息
git config user.name "qyun2012"
git config user.email "qyun@mail2.sysu.edu.cn"

# 3. 创建首次提交
git add .
git commit -m "Initial commit"

# 4. 推送到远程仓库
git push -u origin main

# 5. 验证连接（例如，查看远程仓库信息或拉取一次）
git remote -v
# 或
git fetch origin