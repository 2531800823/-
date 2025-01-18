# windows 系统 git bash 卡顿

#### 如果是 vs code 中卡顿

尝试把这个配置关闭

```
terminal.integrated.shellIntegration.enabled
```

#### 如果是启动和执行命令卡顿的时候

1. 写一个 git bash 脚本来一直执行命令，然后看任务管理器那个占用 cpu 异常

```bash
#!/bin/bash
for i in {1..100}
do
ls
done
```

2. 然后查看任务管理器那个进程占用 cpu 异常，就发现了 MSPCManager Service 这个服务，他是微软的电脑管家，然后尝试把他停止了后，速度变得特别快。
