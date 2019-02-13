## messages.deleteMessages#e58e95d2 flags:# revoke:flags.0?true id:Vector<int> = messages.AffectedMessages

### rpc逻辑
`Deletes messages by their identifiers.`

#### 删除消息逻辑
1. 根据请求封装删除消息的更新
2. 推送到其他设备
3. 从数据库中删除用户的消息 `update message_boxes set deleted = 1 where user_id = ? and user_message_box_id in (?) and deleted = 0`
4. 如果消息是撤回, 推送到对端并从数据库中删除对端消息
5. 封装messages.AffectedMessages `pts`（从redis中获取然后加上删除消息的条数) 和 `ptsCount`(删除消息的条数) 返回rpc请求


### 缺陷
未更新dialog的TopMessage