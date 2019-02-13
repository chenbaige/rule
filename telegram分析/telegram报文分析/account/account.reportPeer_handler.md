```
account.reportPeer#ae189d5f peer:InputPeer reason:ReportReason = Bool
```

---
# 举报用户
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
peer | InputPeer | 举报对象类型
reason | ReportReason | 举报原因

```
InputPeer
	inputPeerEmpty
	inputPeerSelf
	inputPeerChat
	inputPeerUser
	inputPeerChannel

ReportReason
	inputReportReasonSpam
	inputReportReasonViolence
	inputReportReasonPornography
	inputReportReasonOther
	inputReportReasonCopyright
```

## 逻辑
1. 在数据库（reports 表）中记录
2. 返回