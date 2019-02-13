> auth.logOut#5717da40 = Bool;

## rpc逻辑

- 调用auth_session的UnbindAuthKeyUser
- UnbindAuthUser：删除authKeyId及userId对应的数据

##表
- auth_users

## 场景
用户点击登出会触发