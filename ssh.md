### ssh免密登录互连：

同时操作配置公私钥，免密登陆

ssh-keygen -t rsa -P ''
这样每台机就有各自的公私钥

查看是否生成了公私钥
cd ~/.ssh/
ls
当出现id_rsa.pub和 id_rsa两个文件时说明已生成了公私钥

把公钥生成新的文件
cat id_rsa.pub >> authorized_keys

给新的文件授权
chmod 600 authorized_keys
这时三个窗口就都生成了新的文件

每台机都拷贝同样的公钥到另2台机上，这样3台机就可以互相免密登录
ssh-copy-id -i ~/.ssh/id_rsa.pub hadoop2
ssh-copy-id -i ~/.ssh/id_rsa.pub hadoop3
ssh-copy-id -i ~/.ssh/id_rsa.pub hadoop4

解析
ssh- copy-id命令可以把本地的ssh公钥文件安装到远程主机对应的主机名下
注意
因为是同时在操作3个窗口，所以当复制本机的ssh公钥时，会提示报错已存在了公钥，但是另外2台会提示输入密码，不用管报错的，直接同时输入密码就好了，这时就会把公钥复制到另外2台机上。