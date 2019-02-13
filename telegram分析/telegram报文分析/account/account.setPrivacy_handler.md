```
account.setPrivacy#c9f81ce8 key:InputPrivacyKey rules:Vector<InputPrivacyRule> = account.PrivacyRules
```

---
# 设置用户隐私规则
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
key | InputPrivacyKey | 隐私规则类型
rules | Vector\<InputPrivacyRule\> | 隐私规则

```
key
	"KEY_TYPE_INVALID": 0
	"STATUS_TIMESTAMP": 1
	"CHAT_INVITE":      2
	"PHONE_CALL":       3
```

## 逻辑
1. 在数据库（user_privacys 表）中记录
2. 同步