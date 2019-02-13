## messages.toggleChatAdmins#ec8bd9e1 chat_id:int enabled:Bool = Updates

### rpc逻辑
#### 设置是否开启管理员权限
1. 根据chat_id找到群聊
2. 检查操作是否有意义
3. 更新群聊管理员权限设置 `update chats set admins_enabled = ?, version = version + 1 where id = ?`
4. 封装rpc请求返回结果