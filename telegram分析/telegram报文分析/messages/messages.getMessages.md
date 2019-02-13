## messages.getMessages#63c66506 id:Vector<InputMessage> = messages.Messages

### rpc逻辑
`Returns the list of messages by their IDs`
#### 获取消息列表逻辑
1. 根据消息类型筛选需要获取的消息id列表(只支持两种类型TLConstructor_CRC32_inputMessageID、TLConstructor_CRC32_inputMessageReplyTo)
2. 根据消息列表从数据库中获取消息
3. 获取消息相关的用户和群聊信息
4. 封装rpc请求返回

#### 缺陷
获取用户信息时与数据库有太多次交互(遍历用户id列表，然后逐一查询多个用户信息相关表，未使用联合查询）
获取群聊信息时与数据库有太多次交互(遍历群聊id列表, 逐一查询群聊信息）