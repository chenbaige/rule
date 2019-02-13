## messages.getDialogs#b098aee6 flags:# exclude_pinned:flags.0?true offset_date:int offset_id:int offset_peer:InputPeer limit:int hash:int = messages.Dialogs
### rpc逻辑
`Returns the current user dialog list.`
#### 返回用户对话框列表
1. 如果`offset_id`为`0`, 将`offset_id`置为`math.MaxInt32`
2. 从数据库获取用户对话框 	`select ... from user_dialogs where user_id = ? and is_pined = 0 and top_message < offset_id order by top_message desc limit = limit`
3. 根据第2步获取的对话框列表获取对话框消息、框用户以及群聊消息
4. 封装数据返回rpc调用