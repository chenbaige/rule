> auth.signUp#1b067634 phone_number:string phone_code_hash:string phone_code:string first_name:string last_name:string = auth.Authorization

## rpc逻辑

- 解析phoneNumber格式

- 判断phonecode是否为空

- 判断FirstName是否为空

- DoSignIn
    
    - 更新登入次数attempt

    - 从auth_phone_transactions中查找信息，并判断CodeState、CodeExpired预计phoneCode
    
    - 更新CodeState

- 创建User信息

- 绑定authKey

- 创建新账号，此处存的是UserId和ServerSalt


## 表
- users
- auth_phone_transactions
- auth_users