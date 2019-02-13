## messages.editChatPhoto#ca4c79d8 chat_id:int photo:InputChatPhoto = Updates
### rpc逻辑
`Changes chat photo and sends a service message on it`
#### 更改群聊照片逻辑
1. 根据`chat_id`获取群聊信息
2. 根据`photo`类型分别处理
   1. `TLConstructor_CRC32_inputChatPhotoEmpty` 删除照片 `photo_id`为`0`
   2. `TLConstructor_CRC32_inputChatUploadedPhoto` 调用`document` rpc请求上传新照片 `photo_id`从rpc回复中获取
   3. `TLConstructor_CRC32_inputChatPhoto` 未处理 `photo_id`为`0`
3. 更新群聊`photo_id` 以及群聊版本
4. 封装更新消息推送给群聊成员