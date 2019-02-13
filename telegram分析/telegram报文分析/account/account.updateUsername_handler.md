```
account.updateUsername#3e0bdd7c username:string = User
```

---
# 更新用户名
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
username | string | 用户名

## 逻辑
1. 在数据库（username 表和 users 表）中更新 username
2. 同步
3. 返回