### 工具用途
这款工具的主要目的是去爆破日常测试中的JWT密钥，因为传统的爆破方式在java后端中可能存在一些，导致爆破无法成功
### 场景
● 服务端是 java 编写的应用程序  
● 服务端的 jjwt 组件版本在 0.9.1（目前只验证过此版本，更高版本或许也可以）以下  
● 开发人员的错误代码编写，在传递 JWT 的 key 时使用字符串而非字节码数组  
● 字符串相对来说简单  
### 用法
