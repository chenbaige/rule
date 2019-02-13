```
account.setAccountTTL#2442485e ttl:AccountDaysTTL = Bool
```

---
# ？
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
ttl | AccountDaysTTL | 账户保留时间

## 逻辑
1. 在数据库（users 表）中记录 account_days_ttl 的值
2. 返回