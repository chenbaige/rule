## messages.sendMedia#c8f16791 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true peer:InputPeer reply_to_msg_id:flags.0?int media:InputMedia random_id:long reply_markup:flags.2?ReplyMarkup = Updates

### rpc逻辑
`Sends a non-text message.`

#### 发送媒体信息逻辑
1. 检查参数合法性
2. 封装对端信息
3.  如果`clear_draft`为`true`, 清除用户草稿并同步到用户其他设备
4. 封装媒体信息
5. 根据对端类型分别处理（目前暂不支持channel）
6. 封装发件箱消息并插入到数据库`insert ignore into message_boxes` 然后更新数据库对话框信息 `insert into user_dialogs ... on duplicate key update`
7. 封装收件箱并插入到数据库 然后更新数据库对话框信息 如果是群聊则遍历群成员执行这个操作 如果有艾特信息插入到数据库`insert ignore into unread_mentions`
8. 同步到发送者其他设备
9. 推送信息到接收者
10. 封装并返回rpc请求结果

#### 缺陷
没有采用事务

#### 说明
与sendMessage核心逻辑大同小异 区别在于封装消息
