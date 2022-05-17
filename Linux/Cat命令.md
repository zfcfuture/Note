### Cat命令

#### 1.  **cat**

- `cat ./filename`：基础用法，查看文件内容

- `cat -n ./filename`：显示文件前n行内容

- ==新建文件并输入内容==：

  ```shell
  root@localhost:~# cat > filename
  hello
  world
  ctrl + D // 终止输入
  root@localhost:~# cat filename
  hello
  world
  ```

  <font color='red'>Note</font>：再次使用将会cat添加内容时，以前的数据将不复存在

- ==合并文件==:

  ```shell
  root@localhost:~# cat file1.txt file2.txt > file3.txt
  ```

- ==像文件中追加内容==:

  ```shell
  root@localhost:~# cat >> file.txt <<EOF
  hello
  EOF
  root@localhost:~# cat >> file.txt <<EOF
  world
  EOF
  root@localhost:~# cat file.txt
  hello
  world
  ```

- ==清空文件==：

  ```shell
  root@localhost:~# cat file.txt
  > jack
  root@localhost:~# cat /dev/null > file.txt
  >
  root@localhost:~# cat file.txt
  >
  ```

  

- ==可视化修改密码==:

  ```shell
  root@localhost:~# cat <<EOF | passwd
  > 123456 //第一次输入密码
  > 123456 //确认输入密码
  > EOF
  ```

#### 2.  tr

配合cat命令可以实现文本内容的替换：

```shell
root@localhost:~# cat file.txt
> hello
root@localhost:~# cat file.txt | tr [a-z] [A-Z] | cat file.txt
> HELLO
```

