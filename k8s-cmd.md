
# 查看当前集群的所有的节点
kubectl get node
# 显示 Node 的详细信息（一般用不着）
kubectl describe node node1

# 查看所有的pod
kubectl get pod --all-namespaces
# 查看pod的详细信息
kubectl get pods -o wide --all-namespaces

# 查看所有创建的服务
kubectl get service

# 查看所有的deploy
kubectl get deploy

# 重启 pod（这个方式会删除原来的pod，然后再重新生成一个pod达到重启的目的）
# 有yaml文件的重启
kubectl replace --force -f xxx.yaml
# 无yaml文件的重启
kubectl get pod <POD_NAME> -n <NAMESPACE> -o yaml | kubectl replace --force -f -

# 查看pod的详细信息
kubectl describe pod nfs-client-provisioner-65c77c7bf9-54rdp -n default

# 根据 yaml 文件创建Pod资源
kubectl apply -f pod.yaml
# 删除基于 pod.yaml 文件定义的Pod 
kubectl delete -f pod.yaml

# 查看容器的日志
kubectl logs <pod-name>
# 实时查看日志
kubectl logs -f <pod-name>
# 若 pod 只有一个容器，可以不加 -c
kubectl log  <pod-name> -c <container_name>
# 返回所有标记为 app=frontend 的 pod 的合并日志
kubectl logs -l app=frontend

# 通过bash获得 pod 中某个容器的TTY，相当于登录容器
# kubectl exec -it <pod-name> -c <container-name> -- bash
eg:
kubectl exec -it redis-master-cln81 -- bash

# 查看 endpoint 列表
kubectl get endpoints

# 查看已有的token
kubeadm token list