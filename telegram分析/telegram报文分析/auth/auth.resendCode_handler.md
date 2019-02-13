> auth.resendCode#3ef1a9bf phone_number:string phone_code_hash:string = auth.SentCode

## rpc逻辑

- 检查phone code
- 检查手机号格式
- 检查该手机号是否被禁用，查询banned表是否存在该手机号
- 重发code
    
    - DataType检查
    - State检查  (<font color='yellow'>TODO:</font>存在bug状态设置不对，应该会报错)
    - CodeExpired检查   
- 发送code
    - 如果手机号已经注册，检查是否有其他设备在线，有则使用sentCodeTypeApp
    - 否则使用sentCodeTypeSms
    - <font color='yellow'>TODO(@benqi):</font> 有则使用sentCodeTypeFlashCall和entCodeTypeCall

## 表

