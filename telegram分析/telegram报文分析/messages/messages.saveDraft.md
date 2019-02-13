## messages.saveDraft#bc39e14b flags:# no_webpage:flags.1?true reply_to_msg_id:flags.0?int peer:InputPeer message:string entities:flags.3?Vector<MessageEntity> = Bool

### rpc逻辑
#### 存储草稿逻辑
1. 根据请求封装草稿消息
2. 将草稿消息序列化成json字符串存进数据库`update user_dialogs set draft_type = 2, draft_message_data = ? where user_id = ? and peer_type = ? and peer_id = ?`
3. 返回rpc请求`true`

### 缺陷
1. 未检查会话是否存在
2. 未同步其他客户端