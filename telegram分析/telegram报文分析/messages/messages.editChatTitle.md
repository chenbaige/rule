## messages.editChatTitle#dc452855 chat_id:int title:string = Updates
### rpc逻辑
`Chanages chat name and sends a service message on it.`
#### 更新群聊标题逻辑
1. 根据`chat_id`获取群聊信息
2. 检查是用户是否为群聊成员
3. 检查用户否有权限(只有群聊创建者或者管理员有权限）
4. 检查是否无意义的操作
5. 更新群聊标题以及群聊版本
6. 封装更新群聊标题信息 推送给群聊成员