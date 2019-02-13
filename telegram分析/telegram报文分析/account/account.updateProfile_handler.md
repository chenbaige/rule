```
account.updateProfile#78515775 flags:# first_name:flags.0?string last_name:flags.1?string about:flags.2?string = User
```

---
# 更新用户资料
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
first_name | string | 名
last_name | string | 姓
about | string | 简介

## 逻辑
1. 判断是修改简介还是姓名（不能同时修改）
2. 在数据库（users 表）中更新
3. 同步
4. 返回