# git - 基本使用

下载 [git](https://git-scm.com/)

[git大全](https://gitee.com/all-about-git)

1. 在计划工作的文件夹 鼠标右键 打开Git Bash Here

2. 初始化身份信息 依次执行如下命令

```php
git config --global user.name “GitHub用户名”
```

```php
git config --global user.email “GitHub邮箱地址”
```

3. **SSH免密操作**

   Git支持https和ssh两种传输协议（https-每次输入密码，ssh-一次声明永久使用）

   ###### 生成秘钥对

   ```php
   ssh-keygen -t rsa -C "你的GitHub用户邮箱"
   ```

   执行此命令后一路回车

   找到路径 pub文件，将里面的公钥添加到远程仓库github

4. 克隆代码 （下载仓库）

   ```php
   git clone ssh地址
   ```

5. 开始对项目文件 进行代码的增删改等操作

6. 提交到暂存区

   ```php
   git add .
   ```

7. 提交到本地仓库

   ```php
   git commit -m “这里是注释说明，建议必须写”
   ```

8. 提交到远程仓库

   ```php
   git push
   ```

   ​