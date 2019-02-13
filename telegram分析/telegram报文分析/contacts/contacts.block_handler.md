```
contacts.block#332b49fc id:InputUser = Bool
```

---
# 将用户添加到黑名单
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
id | InputUser | user ID

## 逻辑
1. 获取添加到黑名单的 userId（自己还是别人）（拉黑自己？）
2. 检查用户是否存在
3. 在数据库（user_contacts）中将 blocked 字段设为 1
4. 同步
5. 返回