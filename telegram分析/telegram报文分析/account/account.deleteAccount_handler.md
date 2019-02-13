```
account.deleteAccount#418d4e0b reason:string = Bool
```

---
# 删除账户
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
reason | string | 原因

> 删除成功后跳转到注册页面

## 逻辑
1. 在数据库（users 表）中将用户 deleted 设为 1（并没真正删除）
2. 返回