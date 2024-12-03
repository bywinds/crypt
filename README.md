

## 加密软件

通过互联网传输文件，如何保证信息安全呢？

这是用GO语言编写的加密软件，服务端保留在我这里，将客户端复制多份给其他人，就可以实现服务端和客户端加解密文件，而客户端之间却不能解密文件。

这种加密方式，以目前计算机的算力，很难破解，非常安全；同时加密后的文件，经过了压缩，大幅减少体积，便于网络传输。

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

















一、标题写法：
第一种方法：
1、在文本下面加上 等于号 = ，那么上方的文本就变成了大标题。等于号的个数无限制，但一定要大于0个哦。。
2、在文本下面加上 下划线 - ，那么上方的文本就变成了中标题，同样的 下划线个数无限制。
3、要想输入=号，上面有文本而不让其转化为大标题，则需要在两者之间加一个空行。
另一种方法：（推荐这种方法；注意⚠️中间需要有一个空格）
关于标题还有等级表示法，分为六个等级，显示的文本大小依次减小。不同等级之间是以井号  #  的个数来标识的。一级标题有一个 #，二级标题有两个# ，以此类推。
例如：
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题 
二、编辑基本语法  
1、字体格式强调
 我们可以使用下面的方式给我们的文本添加强调的效果
*强调*  (示例：斜体)  
 _强调_  (示例：斜体)  
**加重强调**  (示例：粗体)  
 __加重强调__ (示例：粗体)  
***特别强调*** (示例：粗斜体)  
___特别强调___  (示例：粗斜体)  
2、代码  
`<hello world>`  
3、代码块高亮  
```
@Override
protected void onDestroy() {
    EventBus.getDefault().unregister(this);
    super.onDestroy();
}
```  
4、表格 （建议在表格前空一行，否则可能影响表格无法显示）
 
 表头  | 表头  | 表头
 ---- | ----- | ------  
 单元格内容  | 单元格内容 | 单元格内容 
 单元格内容  | 单元格内容 | 单元格内容  
 
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

