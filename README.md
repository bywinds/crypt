

## 加密软件

通过互联网传输文件，如何保证信息安全呢？

这是用GO语言编写的加密软件，服务端保留在我这里，将客户端复制多份给其他人，就可以实现服务端和客户端加解密文件，而客户端之间却不能解密文件。

这种加密方式，以目前计算机的算力，很难破解，非常安全；同时加密后的文件，经过了压缩，大幅减少体积，便于网络传输。

![客户端](https://filescdn.proginn.com/works/969a653473c322679159ea9ecce52cfc76684879.png)  

<br>

### 程序介绍

1、客户端仅能解密服务器端加密的文件；客户端加密文件时， 使用公钥，椭圆曲线加密算法

2、服务端加密文件时，使用对称密钥，AES加密算法；服务端能解密两种加密的文件

3、对加密文件使用sha256生成签名，保证文件的一致性

4、使用ZIP压缩，AES256加密	

<br>

### 使用方法

将项目下载到本地计算机上，本地计算机需要安装Go的开发环境，以下命令均在项目根目录中进行

__一、创建图标资源__

`windres -o main.syso main.rc`


__二、创建密钥数据__

* 将main.go文件中的 main()  函数注掉，并将 main2()  函数，改成 main() 

* 在命令行窗口执行：`go run main.go`

* 程序执行后，在项目根目录中，生成文本文件：my_crypt.txt，将其中的AES密钥、ZIP密钥、ECC私钥、ECC公钥，对应的字符串依次复制，替换main.go文件中的AesKeys、ZipKeys、X509PrivateKeys、X509PublicKeys对应的值


__三、创建可执行程序__

* 将main.go文件中的 main()  函数注掉，并解除原先的 main()  函数的注释 ；

* 将main.go文件中，常量 IsServer 赋值为 false，执行命令创建客户端：  
* `go build -ldflags="-H windowsgui -w -s" -o E:\Desktop\Client.exe`

* 将main.go文件中，常量 IsServer 赋值为 true，执行命令创建服务端：  
* `go build -ldflags="-H windowsgui -w -s" -o E:\Desktop\Server.exe`

<br>

### 补充说明

* main.go文件中，resourceGongfuPng变量的StaticContent是一张图片对应的字节数组，用于生成密钥时的种子数据，您可以换成其他的字节数组；

* 生成的客户端和服务端的序列号（CN）时一致的 controls="controls" width="500" height="300"

<br>

___如果您对程序有疑问，可以向我询问。如果您支持我的工作，可以送我一杯咖啡，谢谢！___

![打赏](https://private-user-images.githubusercontent.com/19700138/391989395-107781f6-d07b-40d3-bf02-e1b56577104d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzMyMzQyNTEsIm5iZiI6MTczMzIzMzk1MSwicGF0aCI6Ii8xOTcwMDEzOC8zOTE5ODkzOTUtMTA3NzgxZjYtZDA3Yi00MGQzLWJmMDItZTFiNTY1NzcxMDRkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMDMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjAzVDEzNTIzMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRhMjI1OGQwODhhZTc3OWJkN2IyZjk2YjAwOTExZTI3NDBhYzRkOGNkYWQ0M2ZmMzliMjE4ZGZhNTYyMjA3NzkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.Pl7B_wdU1mTwaUB5FzRYpRXMvbvu6rOA7THrjmbXH9A)  

<br>

#### 视频教学

<video src="https://private-user-images.githubusercontent.com/19700138/391949025-cb8e4161-5573-48d4-965c-f7f1e58b8251.mp4"></video>
