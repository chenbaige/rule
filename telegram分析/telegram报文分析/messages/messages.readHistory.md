## messages.readHistory#e306d3a peer:InputPeer max_id:int = messages.AffectedMessages

### rpc逻辑
#### 标记消息为已读逻辑
1. 根据请求更新数据库, 设置会话未读消息为`0` 更新`read_inbox_max_id`. `update user_dialogs set unread_count = 0, read_inbox_max_id = ? where user_id = ? and peer_type = ? and peer_id = ？`
2. 同步到其他设备
3. 更新数据库中`read_outbox_max_id` `update user_dialogs set read_outbox_max_id = ? where user_id = ? and peer_type = ? and peer_id = ?`并推送到对端
4. 封装返回rpc请求