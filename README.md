# k8s
AWS_Training_Kubernetes

Basic:

kubectl的基本语法: kubectl [command] [TYPE] [NAME] [flags]
1. kubectl logs: 打印Pod中容器的日志( kubectl logs <pod-name> )
2. kubectl describe: 显示一个或多个资源的详细状态( kubectl describe nodes <node-name>, kubectl describe pods 描述所有的pods )
3. kubectl apply: 以文件或标准输入为准应用或更新资源( kubectl apply -f example-service.yaml,  kubectl apply -f <directory> 使用directory路径下的任意.yaml/.yml/.json文件创建对象 )
4. kubectl delete: 删除资源( kubectl delete -f pod.yaml 使用文件中指定的类型和名称删除pod,  kubectl delete pods --all 删除所有的pods )

Advanced:

简单描述 Pod, Node, Deployment, Service, Ingress, ReplicaSet, Namespace 概念

Pod: pod是容器的容器，是Kubernetes最小的可部署单位，一个Pod包含一个或者一组container以及他们共用的资源（比如共享的储存volume和共享的IP地址)

Node：是一个具体执行任务的机器，它可以是虚拟机也可以是物理机，一个node可以运行多个pod，每个node都有master统一管理和调度。

Deployment： deployment为Pod提供了一种申明式更新的方式，比如我们可以直接申明需要的pod副本的数量，会有一个controller帮我们检查这个Pod的健康状态，如果它挂了就会再起一个新的pod.

Service: 将运行在一组 Pods上的应用程序公开为网络服务的抽象方法

Ingress： Ingress 是对集群中服务的外部访问进行管理的 API 对象，暴露了从集群外部到集群内的 HTTP 和 HTTPS 路由

ReplicaSet：ReplicaSet是kubernetes中的一种副本控制器，主要作用是控制由其管理的pod，使pod副本的数量始终维持在预设的个数

Namespace：namespace为名称提供了一个范围。资源的name需要在namespace内是唯一的，namespace是在多个用户之间划分cluster的一种方法
