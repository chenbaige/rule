```
account.updateNotifySettings#84be5b93 peer:InputNotifyPeer settings:InputPeerNotifySettings = Bool
```

---
# 更新通知设置
---

## 参数
参数名称 | 类型 | 解释
:-: | :-: | :-:
peer|InputNotifyPeer| 通知来源
settings|InputPeerNotifySettings| 通知设置

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
1. 在数据库（user\_notify\_settings 表）中记录设置，并把 deleted 置为 0
2. 同步
3. 返回