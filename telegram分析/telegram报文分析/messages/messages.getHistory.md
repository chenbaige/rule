## messages.getHistory#dcbb8260 peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:int = messages.Messages

### rpc逻辑
#### 获取聊天记录逻辑
1. 根据请求封装对端信息
2. 从数据库中获取聊天记录
3. 从数据库中获取用户和群聊信息
4. 封装返回rpc请求

### 说明
作者标注目前只适配android客户端