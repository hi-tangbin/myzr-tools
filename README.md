# 工具

## Linux

### stress - 系统压力测试

+ **描述：**`stress` imposes certain types of compute stress on your system

* **示例：**

```shell
# CPU压力测试: 生成4个线程，每个线程执行平方根计算来模拟CPU负载，持续60秒
stress --cpu 4 --timeout 60s

# 内存压力测试: 分配和释放总共512MB的内存，使用4个线程
stress --vm 4 --vm-bytes 512M --timeout 60s

# I/O压力测试: 生成4个线程，每个线程执行磁盘I/O操作（如同步内存到磁盘），持续60秒
stress --io 4 --timeout 60s

# 综合压力测试: 结合以上所有类型的压力测试，例如同时对CPU、内存和I/O施压：
stress --cpu 2 --io 2 --vm 2 --vm-bytes 256M --timeout 60s
```

