## messages.getFullChat#3b831c66 chat_id:int = messages.ChatFull

### rpc逻辑
`Returns full chat info according to its ID.`
#### 获取群聊详细信息逻辑
1. 从数据库中获取群聊基本信息
2. 获取群聊照片 通知设置等详细信息
3. 获取群聊成员信息
4. 封装rpc请求返回

### 缺陷
ExportedInvite(分享链接)和BotInfo未处理