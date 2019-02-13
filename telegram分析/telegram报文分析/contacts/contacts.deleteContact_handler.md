```
contacts.deleteContact#8e953744 id:InputUser = contacts.Link
```

---
# 从列表中删除联系人
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
id | InputUser | user ID


## 逻辑
> 注意：目前实现的逻辑只支持已经注册的联系人.

1. 判断是删除自己还是别人（删除自己？）
2. 检查用户是否存在
3. 在数据库（user_contacts）中将删除的联系人的 is_deleted 设为 1，mutual 设为 0
4. 将删除的联系人与用户的 mutal 设为 0 
5. 同步自己状态和被删除的联系人状态
6. 返回