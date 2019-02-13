## messages.addChatUser#f9a0aa09 chat_id:int user_id:InputUser fwd_limit:int = Updates
### rpc逻辑
`Adds a user to a chat and sends a service message on it`

玩家加入群聊逻辑：
#### 根据chat_id找到群聊
`select ... from chats where id = chat_id`
#### 将玩家添加到群聊成员
##### 获取群聊成员
`select ... from chat_participants where chat_id = ? and state = 0` 
`state=1` 代表被删除 这里不应该筛选`state` 因为曾经被删除的群聊用户再次加入只需更新`state`就行了
##### 将玩家添加到群聊成员
有两种情况:
>* 用户曾经是群聊成员, 这种情况只需要更新数据库中state为0
* 用户第一次加入群聊, 这种情况需要插入心群聊成员到群聊列表信息

##### 更新群聊信息
更新群聊版本号 群聊人数

#### 推送消息
封装用户加入群聊消息 推送给所有群聊成员

