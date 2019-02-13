## 生成秘钥对的方法
1）  
```
ssh-keygen -t rsa -b 4096 -f ~/.ssh/my_rsa  
 ```  
 ~/.ssh/my_rsa是存放的文件名，可以自己设置，中间弹出是否给私钥设置密码，可以直接回车不设置密码，生成的 *.pub 文件是公钥，另一个是私钥  


2）在 .ssh/config里配置gitlab使用的私钥。（如果除了gitlab还有其他的git仓库使用不同的秘钥的话，可以配置多个）
```
# gitlab
Host gitlab.qukuaishequ.com
HostName gitlab.qukuaishequ.com
User 填自己的用户名
IdentityFile ~/.ssh/my_rsa

# other
Host 1.2.3.4
HostName 1.2.3.4
User 填自己的用户名
IdentityFile ~/.ssh/other_rsa  
```

3)  
配置git提交记录里显示的用户名和邮箱：  
```
git config --global user.name "用户名"
git config --global user.email "邮箱"
```