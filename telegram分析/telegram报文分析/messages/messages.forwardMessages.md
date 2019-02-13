## messages.forwardMessages#708e0195 flags:# silent:flags.5?true background:flags.6?true with_my_score:flags.8?true grouped:flags.9?true from_peer:InputPeer id:Vector<int> random_id:Vector<long> to_peer:InputPeer = Updates

### rpc逻辑
`Forwards messages by their IDs`

#### 转发消息逻辑
1. 根据消息id列表从数据库中获取消息列表, 然后封装转发消息
2. 根据对端类型分别处理（目前暂不支持channel）
3. 封装发件箱消息并插入到数据库`insert ignore into message_boxes` 然后更新数据库对话框信息 `insert into user_dialogs ... on duplicate key update`
4. 封装收件箱并插入到数据库 然后更新数据库对话框信息 如果是群聊则遍历群成员执行这个操作 如果有艾特信息插入到数据库`insert ignore into unread_mentions`
5. 同步到发送者其他设备
6. 推送信息到接收者
7. 封装并返回rpc请求结果



#### 缺陷
1. 没有采用事务
2. 根据消息id列表获取消息内容时没有采用联合查询

#### 说明
发送消息的逻辑和sendMultiMedia逻辑一样