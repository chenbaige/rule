```
account.updateStatus#6628562c offline:Bool = Bool
```

---
# 更新用户状态
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
 offline | Bool | 是否离线；如果传输（boolTrue），则用户状态将更改为（userStatusOffline）。

> 注：pc 端离开应用程序激活状态（点击其他应用程序）即为离线，


## 逻辑
1. 如果用户在线，则在数据库（user\_presences 表）中记录在线状态
2. 推送状态
3. 返回