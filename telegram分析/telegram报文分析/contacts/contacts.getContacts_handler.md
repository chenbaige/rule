```
ontacts.getContacts#c023849f hash:int = contacts.Contacts
```

---
# 返回当前用户的联系人列表
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
hash | int | 如果客户端上已存在完整的联系人列表，则可以在此参数中传递以逗号分隔的联系人ID列表的升序的md5-hash。 如果联系人未更改，则将返回「contacts.contactsNotModified」。

## 逻辑
1. 在数据库（user_contacts）中查询当前用户的联系人列表
2. 返回