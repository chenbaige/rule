```
account.registerDevice#5cbea590 token_type:int token:string app_sandbox:Bool secret:bytes other_uids:Vector<int> = Bool
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
app_sandbox|Bool | 如果传输（boolTrue），则在传输期间将使用沙盒证书。
secret|bytes| ？
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
1. 在数据库（devices 表）中记录 state 为 0
2. 返回