

## 加密软件

通过互联网传输文件，如何保证信息安全呢？

这是用GO语言编写的加密软件，服务端保留在我这里，将客户端复制多份给其他人，就可以实现服务端和客户端加解密文件，而客户端之间却不能解密文件。

这种加密方式，以目前计算机的算力，很难破解，非常安全；同时加密后的文件，经过了压缩，大幅减少体积，便于网络传输。






<br>

![图片名称](https://www.baidu.com/img/bd_logo1.png)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![图片名称](https://www.baidu.com/img/bd_logo1.png)  

<br>



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

* 生成的客户端和服务端的序列号（CN）时一致的














 
5、其他引用
图片  
![图片名称](https://www.baidu.com/img/bd_logo1.png)  
链接  
[链接名称](https://www.baidu.com/)    
6、列表 
1. 项目1  
2. 项目2  
3. 项目3  
   * 项目1 （一个*号会显示为一个黑点，注意⚠️有空格，否则直接显示为*项目1） 
   * 项目2   
 
7、换行（建议直接在前一行后面补两个空格）
直接回车不能换行，  
可以在上一行文本后面补两个空格，  
这样下一行的文本就换行了。
或者就是在两行文本直接加一个空行。
也能实现换行效果，不过这个行间距有点大。  
 
8、引用
> 第一行引用文字  
> 第二行引用文字   

Here's a sample video:

![Sample Video](https://github.com/user-attachments/assets/cb8e4161-5573-48d4-965c-f7f1e58b8251)


Here's a sample video:

![Sample Video](https://private-user-images.githubusercontent.com/19700138/391949025-cb8e4161-5573-48d4-965c-f7f1e58b8251.mp4)

9.引用

<video src="https://private-user-images.githubusercontent.com/19700138/391949025-cb8e4161-5573-48d4-965c-f7f1e58b8251.mp4" controls="controls" width="500" height="300"></video>

