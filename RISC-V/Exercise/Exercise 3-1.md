### Exercise 3-1

![image-20210806134325851](C:\Users\E0005175\AppData\Roaming\Typora\typora-user-images\image-20210806134325851.png)

```shell
1.  hello.c
2.  gcc -c hello.c
	ls （hello.c hello.o）
3.  readelf -h hello.o
4.  readelf -SW hello.o
5.  rm hello.o
	gcc -g -c hello.c
	objdump -S hello.o
```

