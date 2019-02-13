## messages.getAllStickers#1c9618b1 hash:int = messages.AllStickers

### rpc逻辑

#### 获取所有表情
1. 从数据库中获取所有表情 `select sticker_set_id, access_hash, title, short_name, count, hash from sticker_sets where hash > 0`
2. 封装rpc请求返回

### 缺陷
未处理hash规则直接返回所有表情 返回时写死hash=0

### 说明
目前数据库中没有任何表情包 且作者没有实现安装表情包接口