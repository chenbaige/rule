```
contacts.deleteContacts#59ab389e id:Vector<InputUser> = Bool
```

---
# 从列表中删除多个联系人
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
id | Vector\<InputUser\>| user ID 列表

## 逻辑
> 注意: 目前实现的逻辑只支持导入 1 个并且已经注册的联系人.

1. 判断是删除自己还是别人（删除自己？）
2. 检查用户是否存在
3. 在数据库（user_contacts）中将删除的联系人的 is_deleted 设为 1，mutual 设为 0
4. 将删除的联系人与用户的 mutal 设为 0 
5. 同步自己状态和被删除的联系人状态
6. 返回