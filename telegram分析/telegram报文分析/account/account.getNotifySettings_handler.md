```
account.getNotifySettings#12b3ad31 peer:InputNotifyPeer = PeerNotifySettings
```

---
# 获取通知设置

> 从「所有用户/所有组」获取当前通知设置给「用户/组」

---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
peer|InputNotifyPeer| 通知来源

```
PeerType:
	PEER_EMPTY   = 0
	PEER_SELF    = 1
	PEER_USER    = 2
	PEER_CHAT    = 3
	PEER_CHANNEL = 4
	PEER_USERS   = 5
	PEER_CHATS   = 6
```

## 逻辑
1. 在数据库（user_notify_settings 表）中获取通知设置，如果数据库中没有则给默认值
2. 返回