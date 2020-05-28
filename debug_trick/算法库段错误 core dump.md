# 算法库段错误 core dump

Linux下算法库so编译时没有可以通过，调用的时候出现core dump，往往是少链接了某些静态库或者存在undefined symbols。

先查找缺少什么：

```c++
ldd -r lib.so
```

然后看undefined symbols是在哪个静态库中

```
c++filt (undefined symbols)
```

