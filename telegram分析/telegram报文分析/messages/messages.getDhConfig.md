## messages.getDhConfig#26cf8950 version:int random_length:int = messages.DhConfig

### rpc逻辑
`Returns configuration parameters for Diffie–Hellman key generation. Can also return a random sequence of bytes of required length.`
返回迪菲霍夫曼配置 目前是直接设定的p、g以及version 设置随机数