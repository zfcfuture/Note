### 登录HAPS

1.   登录ETX
2.   连接haps：  `ssh -X [haps01@10.12.208.30](mailto:haps01@10.12.208.30)`，密码：`haps80`
3.   拷贝文件到haps：`scp -P 22 zfc@10.12.100.12:~/file_dir ~/zfc`
4.   运行Confpro GUI：`confpro_gui &`
5.   弹出对话框后选择 **Platform --> Select System**
6.   如果HAPS板已上电且和PC连接好，则会列出==“Available Systems”==，选中并点击“Select”按钮，加载配置
7.   更新配置和bitfile：在HAPS Configuration Tool界面点击“Config System”，选择.conf配置文件。双击conf文件，或者点击“Open”按钮，加载配置，等待更新完成
8.   新开一个窗口运行putty，命令为：`~/putty &`，创建或选择一个session，注意波特率为38400（如果报错，一般是==文件权限不足==，**运行命令**：`sudo chmod 666 /dev/ttyUSB0`
9.   新开一个终端，存放tcl脚本，启动cpu：`confprosh xxx.tcl`
10.   新开一个终端，启动OpenOCD：`./openocd -f xxx.cfg`
11.   新开一个终端，启动gdb：`riscv64-unknown-elf-gdb`
12.   在gdb中监听端口：`target remote:3333`
13.   加载文件：`file file_dir`         `thread apply all load`   
14.   输入C即可执行代码