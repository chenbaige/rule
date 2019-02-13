```
contacts.unblock#e54100bd id:InputUser = Bool
```

---
# 从黑名单中删除用户
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
id | InputUser | user ID

## 逻辑
1. 获取从黑名单中删除的 userId（自己还是别人）（解除拉黑自己？）
2. 检查用户是否存在
3. 在数据库（user_contacts）中将 blocked 字段设为 0
4. 同步
5. 返回