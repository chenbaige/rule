```
account.resetNotifySettings#db7e1747 = Bool
```

---
# 重置通知设置
---

## 参数
不需要参数

## 逻辑
1. 在数据库（user_notify_settings 表）中将用户的 deleted 置为 1（并没有正在删除）
2. 返回