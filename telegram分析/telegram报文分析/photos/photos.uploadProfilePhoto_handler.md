```
photos.uploadProfilePhoto#4f32c098 file:InputFile = photos.Photo
```

---
# 更新当前用户个人资料照片
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
file | InputFile | 通过上传保存的文件

## 逻辑
1. 获取文件
2. 保存到 document server 的 nbfs client 中
3. 在数据库（users 表）中更新用户个人资料照片
4. 返回
