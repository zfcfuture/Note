### tar命令

#### 1.  命令详解

**独立命令**（必选且只能选一个）：

```shell
1  -c: 建立压缩档案
2  -x：解压
3  -t：查看内容
4  -r：向压缩归档文件末尾追加文件
5  -u：更新原压缩包中的文件
```

**可选命令**：

```shell
-z：有gzip属性的
-j：有bz2属性的
-J：具有xz属性的（注3）
-Z：有compress属性的
-v：显示所有过程
-O：将文件解开到标准输出
```

还有一个重要的参数**`-f`**，这是必须的，它的作用是使用文档名字

#### 2.  解压

相比较压缩，我们可能使用解压命令的情况更多，下面是列举的是常见的tar包的解压方式

```shell
tar –xvf file.tar 		 //解压tar
tar -zxvf file.tar.gz 	 //解压tar.gz

tar -xjvf file.tar.bz2   //解压 tar.bz2
tar –xZvf file.tar.Z     //解压tar.Z
unrar e file.rar         //解压rar
unzip file.zip           //解压zip
```

#### 3.  压缩

```shell
tar -cvf file.tar file   	//压缩为tar包
tar -zcvf file.tar.gz file  //压缩为tar.gz包
```

