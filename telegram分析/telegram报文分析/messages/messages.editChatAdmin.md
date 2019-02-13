## messages.editChatAdmin#a9e69f2e chat_id:int user_id:InputUser is_admin:Bool = Bool

### rpc逻辑

#### 编辑群聊管理员逻辑
1. 检查请求的`user_id`是否合法
2. 根据`chat_id`获取群聊信息
3. 检查权限(只有群聊创建者可以编辑群聊管理员）
4. 检查操作合法性(避免无意义的操作）
5. 根据is_admin设置管理员或者取消管理员 并更新数据库
6. 更新群聊版本