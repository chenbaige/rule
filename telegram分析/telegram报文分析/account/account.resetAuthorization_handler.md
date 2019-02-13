```
ccount.resetAuthorization#df77f3bc hash:long = Bool
```

---
# 重置授权
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
hash | long | hash 值

## 逻辑
1. 在数据库（auth_users 表）中查询记录
2. 在数据库（auth_users 表）中该条记录的 deleted_at 设为当前时间
3. 返回