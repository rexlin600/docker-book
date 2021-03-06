# 容器生命周期

要了解容器的生命周期，就不得不再次放出我们前面多次强调的 **Docker Commands Diagram** 了，如下：

![](../.gitbook/assets/image%20%283%29%20%281%29.png)

## 生命周期

首先我们知道，容器是由镜像创建而来，可以通过 `create` 或 `run` 命令创建容器。假如你不看上图，对于一个处于 `运行中` 状态的东东，我们可以猜测他可能还有诸如：`停止`、`暂停` 等状态。

如果你是一个 `Javaer`，你可能对于线程的五种状态比较熟悉了：`NEW`、`RUNNABLE`、`RUNNING`、`BLOCKED`、`DEAD` 等。相比之下，容器的生命周期就简单多了，如上图。

容器的各种生命周期的状态流转也比较简单，从上图我们可以非常清晰的看出，下面我们用偏文字化的方式来描述容器的生命周期的各个状态流转：

* 镜像（`image`）通过 `create/run` 创建一个处于 `Stop/Running` 状态的容器；
* 处于 `Stop` 状态的容器可以使用 `start` 指令到 `Running` 状态；
* 处于 `Running` 状态的容器也可以通过 `stop/kill` 指令进入到 `Stop` 状态；
* 处于 Running 状态的容器还可以通过 `pause/unpause` 指令进行 `Pause` 与 `Running` 状态的切换

