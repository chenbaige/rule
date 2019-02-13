##help.getConfig#c4f9186b = Config
### 初始化TLConfig
rpc服务启动时读取配置文件`./config.json`初始化配置
### rpc逻辑
复制一份配置并设置当前时间和过期时间返回给调用者