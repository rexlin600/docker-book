# 进入/退出容器

当我们使用 `-d` 参数使容器在后台运行时，可能我们会因为需要执行某些操作而进入容器，此时我们可以使用 Docker 提供的下面两个命令：

* **docker attach**
* **docker exec（推荐）**

## attach 命令

使用 `attach` 命令虽然可以进入到容器，但是它也存在一个弊端，那就是如果从当前的输入输出中 exit 会导致容器的停止，这当然不是我们想要的效果，这里就不再对这个命令的使用多做介绍了。

## exec 命令

使用 `exec` 命令是推荐的命令，它可以在运行的容器中执行一个命令，这样我们就可以搭配 `-it` 参数从而给容器分配一个以交互模式运行的伪终端从而实现访问容器的目的。

```text
# 运行一个 ubuntu
$ docker run -dit ubuntu
69d137adef7a8a689cbcb059e94da5489d3cddd240ff675c640c8d96e84fe1f6

# 以交互式伪终端访问容器，然后就可以看到熟悉的 Linux 命令提示符
$ docker exec -it 69d1 bash
root@69d137adef7a:/#
```

如果我们从这个 `stdin` 中 `exit`，并不会导致容器的停止，因此推荐大家使用 `exec` 命令。

