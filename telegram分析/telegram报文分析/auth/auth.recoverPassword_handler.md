> auth.recoverPassword#4ea56e92 code:string = auth.Authorization

## rpc逻辑
- 检查request.code是否为空
- 根据userId从user_passwords表中找到对应数据
- 返回用户信息

## 表
- user_passwords
- user