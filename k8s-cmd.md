### 学习kubernetes的核心，就是学习如何对Pod、控制器、Service、存储等各种资源进行操作

### namespaces
  kubectl create ns xxx #创建xxx名字空间
  
  kubectl get ns # 查看所有名字空间
  
  kubectl get ns default # 查看default名字空间
  
  kubectl get ns default -o yaml #指定输出yaml格式
  
  kubectl describe ns default #查看default名字空间详情

### nodes
  kubectl get nodes -o wide # 查看当前集群的所有的节点

### pods
  kubectl get pod -n default #查看default名字空间的pod

  kubectl describe node node1 # 显示 Node 的详细信息

  kubectl get pod --all-namespaces # 查看所有的pod

  kubectl get pods -o wide --all-namespaces # 查看pod的详细信息

  kubectl get pods --show-labels -n default # 查看每个 Pod 自动生成的标签

  kubectl get service # 查看所有创建的服务

### Deployment

  kubectl get deploy -n xxx -o wide #查看xxx名字空间的deploy

  kubectl describe deploy cloud-xxx -n default #查看default名字空间的cloud-xxx的deploy信息

  kubectl get deployment cloud-xxx -o yaml -n default #查看default名字空间的cloud-xxx的deploy的yaml信息

  kubectl get rs -n default #查看 Deployment 创建的 ReplicaSet

### services
  kubectl replace --force -f xxx.yaml # 有yaml文件的重启

  kubectl get pod <POD_NAME> -n <NAMESPACE> -o yaml | kubectl replace --force -f - # 无yaml文件的重启

  kubectl describe pod nfs-client-provisioner-65c77c7bf9-54rdp -n default # 查看pod的详细信息

  kubectl apply -f pod.yaml # 根据 yaml 文件创建Pod资源

  kubectl delete -f pod.yaml # 删除基于 pod.yaml 文件定义的Pod 

  kubectl logs <pod-name> # 查看容器的日志

  kubectl logs -f <pod-name> # 实时查看日志

  kubectl log  <pod-name> -c <container_name> # 若 pod 只有一个容器，可以不加 -c

  kubectl logs -l app=frontend # 返回所有标记为 app=frontend 的 pod 的合并日志

  kubectl exec -it <pod-name> -c <container-name> -- bash # 通过bash获得 pod 中某个容器的TTY，相当于登录容器

  kubectl get endpoints # 查看 endpoint 列表

  kubeadm token list # 查看已有的token

