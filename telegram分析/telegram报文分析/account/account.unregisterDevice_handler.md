```
account.unregisterDevice#3076c4bf token_type:int token:string other_uids:Vector<int> = Bool
```

---
# 反注册设备
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
token_type|int| token 类型
token|string | 设备 token
other_uids|Vecto\<int\> | ？

```
TokenType:
	TOKEN_TYPE_APNS         = 1
	TOKEN_TYPE_GCM          = 2
	TOKEN_TYPE_MPNS         = 3
	TOKEN_TYPE_SIMPLE_PUSH  = 4
	TOKEN_TYPE_UBUNTU_PHONE = 5
	TOKEN_TYPE_BLACKBERRY   = 6

	// Android 里使用
	TOKEN_TYPE_INTERNAL_PUSH = 7

	// web
	TOKEN_TYPE_WEB_PUSH = 10
```

## 逻辑
1. 在数据库（devices 表）中将 state 置为 1，清空除 state，auth\_key\_id，user\_id 的其他字段（sql 语句存在错误，多余一个 token\_type）
2. 返回