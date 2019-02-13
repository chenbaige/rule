## Modules 模块：
是package的集合

## 一、怎么启用module功能
安装 go.1.11 以后的版本，然后选用如下的其中一种方式  
1）export GO111MODULE=on  
2）export GO111MODULE=auto（不设置的话，默认是auto)，工程不在 $GOPATH/src 并且 执行go 命令的目录或者其父目录存在 go.mod 文件  
3）其他场景使用的是老的GOPATH模式

## 二、工作机制
1）通过 go.mod 记录外部依赖的module及其版本情况  
2）go tools 命令（go build，go get 等）会分析源码，把 go.mod 里缺失的依赖补齐。  
3）检查本地是否存在（ $GOPATH/pkg/mod）对应模块的对应版本的代码，并且hash值一直，否则会从对应地址拉取该模块

## 三、工程组织


## 四、主要的元文件
go.mod  
go.sum  

v0.0.0-yyyymmddhhmmss-abcdefabcdef

## 五、版本系统（semantic versioning）
X.Y.Z-pre-release_version
1.0.0-alpha.1
1. MAJOR version when you make incompatible API changes,
2. MINOR version when you add functionality in a backwards-compatible manner, and
3. PATCH version when you make backwards-compatible bug fixes.
参考：
https://semver.org/

如果是v0 或者 v1，则在import path的地方不需要加 vx，大于2得加
使用了modules机制的包，必须在vx的x大于2时，import path上要体现版本
 1.9.7+, 1.10.3+ 后面的版本可以识别 /vx

## 六、常用命令

\# 初始化一个module，会自动生成 go.mod  
>`go mod init mudpellet.com/test`

\# 去除go.mod中不用的模块，补全所需依赖（包括所有平台的依赖，go build只会下载本平台的依赖）  
go mod tidy

\# 会更新go.mod 文件  
go mod edit -require  
go mod edit -replace  
go mod edit -exclude  

\# 查看当前工程的依赖树  
go mod graph

\# 如下会升级 vA.B.C 里的 B 和 C 的更高版本  
go get -u

\# 升级patch版本，X.Y.Z 里的 Z  
go get -u=patch

\# 升级到指定版本  
go get package@version

## 七、goproxy  
export GOPROXY=https://proxy_addr

## 八、FAQ
1.如何解决本地间的module依赖？
go build ./...
go get ./...

## 九、参考资料

https://tonybai.com/2018/07/15/hello-go-module/  
https://github.com/golang/go/wiki/Modules  
https://tonybai.com/2018/07/15/hello-go-module/  
https://goproxy.io/


