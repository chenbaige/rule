```
account.registerDevice#637ea878 token_type:int token:string = Bool
```

---
# 设备注册

>注册设备以便将来发送 PUSH 通知。

---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
token_type|int| token 类型
token|string | 设备 token

## 逻辑
1. 在数据库（devices 表）中记录 state 为 0
2. 返回