### 1. Generate an SSH Key on Mac and Linux 

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

```
this command will create a new SSH key using the email as a label.

使用这个命令会生成公钥和私钥，生成的过程会询问是否加密，可以加密也可以不加密。如果加密那么以后每次使用私钥都需要输入秘密。

### 2. 然后把公钥复制到剪贴板

```
wl-copy < ~/.ssh/id_rsa.pub
```

### 3. 把公钥放到github上去

登录到github.com，进入个人设置，选择 "SSH and GPG keys"，点击 "New SSH key"，将公钥粘贴到 "Key" 文本框中，点击 "Add SSH key" 完成添加。

### 4. 使用方法

在github上创建一个仓库，然后使用

```
git clone ssh地址
```

这时候就可以使用仓库了。
