```
account.getPrivacy#dadbc950 key:InputPrivacyKey = account.PrivacyRules
```

---
# 获取用户隐私规则
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
key | InputPrivacyKey | 隐私规则类型

```
key
	"KEY_TYPE_INVALID": 0
	"STATUS_TIMESTAMP": 1
	"CHAT_INVITE":      2
	"PHONE_CALL":       3
```

## 逻辑
1. 在数据库（user_privacys 表）中查询
2. 返回