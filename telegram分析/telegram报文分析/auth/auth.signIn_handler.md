> auth.signIn#bcd51581 phone_number:string phone_code_hash:string phone_code:string = auth.Authorization

## rpc逻辑

- 检查手机号格式

- 检查request.PhoneCode

- MakeCodeDataByHash

- 检查手机号已经是否存即注册

- DoSignIn
    
    - 更新登入次数attempt

    - 从auth_phone_transactions中查找信息，并判断CodeState、CodeExpired预计phoneCode
    
    - 更新CodeState

- 获取users并绑定authKeyId

- Check SESSION_PASSWORD_NEEDED

## 表

- auth_phone_transactions
- users