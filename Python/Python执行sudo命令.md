### Python执行sudo命令

在编写python脚本时，经常需要用python来执行shell命令，有以下四种方式可以实现在python中执行shell命令：`os.system()`；`os.popen`；`commands模块`；`subprocess模块`

还有一些情况我们需要直接在python直接调用shell脚本，可以采用`os.system()`；`os.popen`两种方式

现有一种情况，我们在python中执行shell命令的时候，需要管理员权限，即带suso的shell命令，具体可以使用以下这种方式：

```python
# 方式一
def test():    
    sudoPassword = 'test'
    command = '/opt/lampp/lampp stopmysql'
    str = os.system('echo %s|sudo -S %s' % (sudoPassword, command))   
    print str
    
# 方式二
(status, result)=commands.getstatusoutput('echo %s| sudo -S %s' %(PASSWORD,cmd))
```

