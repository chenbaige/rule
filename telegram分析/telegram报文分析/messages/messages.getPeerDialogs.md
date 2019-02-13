## messages.getPeerDialogs#e470bcfd peers:Vector<InputDialogPeer> = messages.PeerDialogs

### rpc逻辑
#### 获取对话框对端信息
1. 根据请求里的对端参数信息从数据库获取对话框`	select ... from user_dialogs where user_id = ? and peer_type = ? and peer_id = ?"`
2. 获取对话框相关的用户和群聊信息
3. 调用`sync_client.GetSyncClient().SyncGetState`同步状态
4. 封装返回rpc请求

### 说明
未考虑channel