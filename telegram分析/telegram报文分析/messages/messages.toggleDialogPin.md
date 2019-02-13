## messages.toggleDialogPin#a731e257 flags:# pinned:flags.0?true peer:InputDialogPeer = Bool

### rpc逻辑

#### 选择是否置顶对话框
1. 检查参数
2. 根据请求填充参数更新对话框置顶设置
`update user_dialogs set is_pinned = ? where user_id = ? and peer_type = ? and peer_id = ?`
3. 通知用户其他客户端
4. rpc请求返回true
