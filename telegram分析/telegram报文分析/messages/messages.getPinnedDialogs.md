## messages.getPinnedDialogs#e254d64e = messages.PeerDialogs

### rpc逻辑
#### 获取置顶对话框列表
1. 根据用户获取玩家置顶对话框列表 `select ... from  user_dialogs where user_id = ? and is_pinned = 1 order by top_message desc`
2. 根据第1步获取的对话框列表获取对话框消息、框用户以及群聊消息
3. 调用sync_client.SyncGetState获取同步信息(pts) `pts:Number of events occured in a text box`
4. 封装返回rpc