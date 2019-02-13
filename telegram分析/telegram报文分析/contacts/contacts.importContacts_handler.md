```
contacts.importContacts#2c800be5 contacts:Vector<InputContact> = contacts.ImportedContacts
```

---
# 导入联系人

>在服务器上保存完整联系人列表，将已注册的联系人添加到联系人列表，返回添加的联系人及其信息。

---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
contacts | Vector\<InputContact\> | 导入的联系人列表

## 逻辑
```
调用场景
	1.导入通信录
	2.导入单个联系人
```

1. 将导入的联系人分成联系人列表和手机号码列表（没用到）
2. 在数据库（phone_books 表）中保存联系人列表
3. 从数据库（users 表）中找出导入联系人列表中已注册的用户分类为「我的联系人」和「反向联系人」并标记
4. 未注册的联系人插入数据库（unregistered_contacts 表），已注册的联系人且已经是好友则用导入的联系人信息在数据库（user_contacts 表）中更新联系人信息。如果用户是联系人的反向联系人，则将数据库（user_contacts 表）中联系人的 mutual 标志设为 1，如果不是反向联系人，则在数据库（imported_contacts）表中记录，在数据库（user_contacts）表记录新的联系人
5. 在数据库（popular_contacts 表）中更新联系人共同导入人数
5. 同步并推送给联系人
6. 返回