## 龙芯（Loongson）下解决so中存在的undefined symbol问题

今天在loongson平台下使用cmake编译算法库，静态加载了opencv，编译可以正常通过，在调用的时候出现了undefined symbol的错误：

```c++
undefined reference to `pthread_spin_destroy'
undefined symbol: _ZN2cv8cvtColorERKNS_11_InputArrayERKNS_12_OutputArrayEii     (./libSsDuck.so)
```

第一个错误比较好定义，应该是没有链接-lpthread，在调用的时候或编译静态库的时候加上-lpthread就可以  

第二个错误，需要定位未定义的具体位置：

```c++
ldd -r libs_name
```

找到未定义的符号

```
c++filt undefined symbol
```

找到未定义的具体位置

```c++
cv::cvtColor(cv::_InputArray const&, cv::_OutputArray const&, int, int)
```

出现在一个静态编译的opencv里面，如果没有缺少库或者编译错误，那基本上是库的顺序错误，opencv有一定依赖顺序。

imgproc依赖core，在顺序应该为：opencv_imgproc  opencv_core

这两个应该放在其他库的后面



