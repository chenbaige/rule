## messages.readMessageContents#36a73f77 id:Vector<int> = messages.AffectedMessages

### rpc逻辑
#### 用户读消息内容逻辑
1. 根据请求中的消息id列表从数据库中获取消息
`select ... from message_boxes where user_id = ? and deleted = 0 and user_message_box_id in (?) order by user_message_box_id desc"`
`select ... from message_datas where message_data_id in (?)"`
2. 如果消息中艾特消息在数据库中更新消息为已读 更新用户未读艾特消息数量 删除此条未读艾特消息
3. 同步已读消息id列表到其他设备
4. 封装返回rpc请求
