```
contacts.resolveUsername#f93ccba3 username:string = contacts.ResolvedPeer
```

---
# 解析用户名
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
username | string | 用户名

## 逻辑
1. 从数据库（username）中判断用户名是否存在
2. 判断用户名类型是否正确
3. 返回