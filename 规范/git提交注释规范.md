 ### commit提交信息的模板：  
 ```
A:(B #C) 简单描述

详细描述（可选）
```

### 各个字段说明：
- A（类型）    
feat：需求  
fix: 修复bug  
docs: 修改文档  
refactor：重构，不涉及到需求变动和bugfix  

- B（模块）  
比如：登录，注册，通讯录

- C（issue编号）  
比如：1,2,32

### 示例  
- 需求  
feat:(login #1) 选择国家码  

- 解决修复bug  
fix:(pkg/send #257) 修复选择国家码出现崩溃的情况

- 调整工程结构  
refactor:(comm/crc #56) 调整目录结构

- 更新文档  
docs:(build #57) 修改脚本描述