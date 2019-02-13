## messages.getChats#3c6aa187 id:Vector<int> = messages.Chats
### rpc逻辑
`Returns chat basic info on their IDs.`

#### 获取群聊列表
1. 遍历request中的群聊id列表逐一从数据库中获取群聊基本信息
`select id, creator_user_id, access_hash, participant_count, title, photo_id, admins_enabled, deactivated, version, `date` from chats where id = ?"`
2. 封装rpc请求返回

### 缺陷
遍历列表逐一从数据库中查询效率很低
