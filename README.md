# 工具

* 仓库地址：[[Gitee]](https://gitee.com/myzr/myzr-tools)  [[GitHub]](https://github.com/hi-tangbin/myzr-tools.git)
* 克隆仓库：

```shell
git clone https://gitee.com/myzr/myzr-tools.git
# or
git clone https://github.com/hi-tangbin/myzr-tools.git
```

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

### iperf3 - 网络压力测试

* **描述：** `iperf3` 是用于执行网络吞吐量测量的工具。

* **示例：**

```shell
# 服务端 =======================================================================
iperf3 -s

# 客户端 =======================================================================
## TCP传输测试: 服务器 192.168.137.81，持续10秒，每秒报告一次结果
iperf3 -c 192.168.137.81 -t 10 -i 1
## UDP传输测试: 服务器 192.168.137.81，带宽上限为1000Mbps，持续10秒，每秒报告一次结果
iperf3 -c 192.168.137.81 -u -b 1000M -t 10 -i 1
## 多线程测试: 服务器 192.168.137.81，同时使用4个线程进行测试
iperf3 -c 192.168.199.2 -P 4
```