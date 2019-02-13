```
contacts.search#11f812d8 q:string limit:int = contacts.Found
```

---
# 搜索
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
q | string | 搜索内容
limit | int | 要返回的列表元素的数量

## 逻辑
1. 判断 limit > 0 并且 q 的长度大于等于 5 
2. 在数据库（users）中模糊搜索非好友的联系人（逻辑不太对且实现效果不全）
3. 返回