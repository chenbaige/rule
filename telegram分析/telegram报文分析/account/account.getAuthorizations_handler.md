```
account.getAuthorizations#e320c158 = account.Authorizations
```

---
# 获取授权列表
---

## 参数
不需要参数

## 逻辑
1. 在数据库（auth_users 表）中查询前 6 条记录
2. 返回