### 工具用途
这款工具的主要目的是去爆破日常测试中的JWT密钥，因为传统的爆破方式在java后端中可能存在一些，导致爆破无法成功
具体原理可以看文章  
https://www.yuque.com/honghong-h6nk2/kb/zbcrkwbh4z4bk7u5?singleDoc
### 场景
● 服务端是 java 编写的应用程序  
● 服务端的 jjwt 组件版本在 0.9.1（目前只验证过此版本，更高版本或许也可以）以下  
● 开发人员的错误代码编写，在传递 JWT 的 key 时使用字符串而非字节码数组  
● 字符串相对来说简单  
### 用法
![image](https://github.com/user-attachments/assets/47a2d829-beaa-421a-a915-65a7e0f96765)
此工具提供了两种模式，一种是字符串模式，另一种是文件模式
#### 字符串模式
字符串模式就是单个jwt字符串爆破，使用-j命令
```
$# java -jar jwt_brute_8.jar -j eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.mFfnNtm7avaD-MouLptQGvQqpg86nh7iCSyv2NJpZRY -i 1_Common_Password.txt
```
![image](https://github.com/user-attachments/assets/d070a7ff-3992-48d4-888a-99811c59baa4)
(不要惊讶爆破成功多个密钥，因为这些密钥经过处理后最终都一样)
#### 文件模式
文件模式用于爆破存在多个目标站点的情况，可以将多个jwt放到文件中然后批量爆破
使用命令-l
```
$# java -jar jwt_brute_8.jar -l 2.txt -i 1_Common_Password.txt
```
![image](https://github.com/user-attachments/assets/a241ffb3-a83d-4f10-a05f-a402f3e3b56e)
