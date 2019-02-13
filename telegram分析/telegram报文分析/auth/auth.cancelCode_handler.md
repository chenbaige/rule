> auth.cancelCode#1f040578 phone_number:string phone_code_hash:string = Bool

## rpc逻辑
- 检查phone code，即PhoneCodeHash是否空
- 检查手机号格式是否正确
- 更新auth_phone_transactions表的相关数据的state为kCodeStateDeleted
- 返回是否更新成功

## 表
- auth_phone_transactions