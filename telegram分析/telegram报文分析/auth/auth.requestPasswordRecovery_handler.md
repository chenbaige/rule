> auth.requestPasswordRecovery#d897bc66 = auth.PasswordRecovery

## rpc逻辑
 - 根据user_id查询user_passwords的数据
    - 检查server_salt,salt,hash的长度
    - 返回相关数据
        ```go
            data := &passwordData{
            userId:     userId,
            serverSalt: serverSalt,
            salt:       salt,
            hash:       hash,
            hint:       do.Hint,
            email:      do.Email,
            state:      int(do.State),
            dao:        m.dao,
        }
        ```
- 返回一个包含用户email的数据

## 表
- user_passwords