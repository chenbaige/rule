> auth.sendCode#86aef0ec flags:# allow_flashcall:flags.0?true phone_number:string current_number:flags.0?Bool api_id:int api_hash:string = auth.SentCode;

## rpc逻辑

- <font color='yellow'>TODO(@benqi)</font>: 接入telegram网络首先必须申请api_id和api_hash，验证api_id和api_hash是否合法

- 检查手机号格式

- 检查该手机号是否被禁用

- 检查手机号已经是否存在即注册

- DoSendCode

    - makeCodeType:设置codeType
        - kCodeType_None      = 0

        - kCodeType_App       = 1

        - kCodeType_Sms       = 2

        - kCodeType_Call      = 3

        - kCodeType_FlashCall = 4

    - 设置code相关属性，如codeExpired时间

    - auth_phone_transactions插入相关数据

- 返回To_Auth_SentCode

## 表
- banned
- users
- auth_phone_transactions