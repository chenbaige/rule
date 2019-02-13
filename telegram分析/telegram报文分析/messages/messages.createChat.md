## messages.createChat#9cb126e users:Vector<InputUser> title:string = Updates
### rpc逻辑
`Creates a new chat.`

#### 创建群聊逻辑
##### 检查请求参数
* 检查群聊标题是否为空
* 检查群聊人数是否超过200
* 检查群聊成员是否合法

##### 创建群聊
1. check flood_wait(限制用户10s内不能再次创建群聊）
2. 插入群聊信息到数据库 `insert into chats ...`
3. 插入群聊成员信息到数据库 `insert into chat_participants`

##### 推送消息
封装创建群聊消息 推送给群成员