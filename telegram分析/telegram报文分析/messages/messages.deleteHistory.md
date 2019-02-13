## messages.deleteHistory#1c015b09 flags:# just_clear:flags.0?true peer:InputPeer max_id:int = messages.AffectedHistory

### rpc逻辑

#### 删除聊天记录
1. 检查参数, 封装对端信息
2. 根据just_clear是否为true分别处理
3. just_clear为true, 只删除历史记录。 从数据库获取需要删除的message id列表以及最后一条消息 同步到其他客户端 删除消息
4. just_clear为false, 删除整个对话.  从数据库获取需要删除的message id列表 同步到其他客户端 删除消息  设置表`user_diologs`对应玩家会话`top_message`为`0`
5. 封装返回rpc请求