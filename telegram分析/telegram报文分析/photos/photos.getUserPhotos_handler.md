```
photos.getUserPhotos#91cd32a8 user_id:InputUser offset:int max_id:long limit:int = photos.Photos
```

---
# 返回用户个人资料照片列表
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
user_id | InputUser | user ID
offset | int | 跳过的列表元素数
max_id | int | 如果传输了正值，则该方法仅返回ID小于设置值的照片
limit | int | 要返回的列表元素的数量

## 逻辑
1. 判断是返回自己还是别人的照片列表（别人可能不在联系人列表中）
2. 从数据库（users 表）根据 userId 查询照片列表
3. 返回