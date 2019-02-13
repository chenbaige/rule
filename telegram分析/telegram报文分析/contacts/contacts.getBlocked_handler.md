```
contacts.getBlocked#f57c350f offset:int limit:int = contacts.Blocked
```

---
# 返回被拉黑的用户列表
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
offset | int | 跳过的列表元素数
limit | int | 要返回的列表元素的数量

## 逻辑
1. 在数据库（user_contacts）中查询被拉黑的用户列表
2. 返回（构建返回类型时逻辑混乱，应该有问题）