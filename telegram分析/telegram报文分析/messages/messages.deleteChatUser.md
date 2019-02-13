## messages.deleteChatUser#e0611f16 chat_id:int user_id:InputUser = Updates

### rpc逻辑
`Deletes a user from a chat and sends a service message on it.`

#### 从群聊中删除一个群聊成员逻辑
1. 检查`user_id`是否为空
2. 根据`chat_id`获取群聊信息
3. 检查是否有权限（只有创建者可以踢群聊成员 或者成员自己离开）
4. 获取群聊成员列表
5. 检查`user_id`是否在群聊成员列表中
6. 将被删除群聊成员`state`置为1
7. 更新群聊信息 version 群成员数
8. 推送消息给所有群聊成员