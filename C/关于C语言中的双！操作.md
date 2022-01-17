### 关于C语言中的双！操作

<font color="red">**!!**</font> 是为了将其它数据类型向bool值转换，将输出结果固定为0（false）或1（true）

```c
int main(void)
{
    int ret, ret1, ret2;
    ret = 0xe03;

    ret1 = !ret;
    ret2 = !!ret;

    printf("ret1 = %d\n", ret1);
    printf("ret2 = %d\n", ret2);

    return 0;
}
/*****result*****/
ret1 = 0
ret2 = 1
```

