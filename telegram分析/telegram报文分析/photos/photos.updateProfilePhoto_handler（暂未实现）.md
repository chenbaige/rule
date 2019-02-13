```
photos.updateProfilePhoto#f0bb5152 id:InputPhoto = UserProfilePhoto
```

---
# 将以前上传的照片设置为个人资料照片
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
id	| InputPhoto | 输入的照片

## 逻辑
1. 判断照片是否为空
2. 从 document server 中的 nbfs client 中读取照片
3. 同步（暂未实现）
4. 返回