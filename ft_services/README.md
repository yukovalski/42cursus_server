    eval $(~/.linuxbrew/bin/brew shellenv)
    eval $(minikube docker-env)

    minikube start --vm-driver=virtualbox
    minikube status
    
    normal:
    type: Control Plane
    host: Running
    kubelet: Running
    apiserver: Running
    kubeconfig: Configured
    timeToStop: Nonexistentstatus

`minikube stop` — останавливает наш кластер.

`minikube delete` — удаляет наш кластер. Если вы устроили бардак лучше удалите текущий кластер и заново разверните новый.

`minikube dashboard` — запускает наш Kubernetes web-dashboard. Если он запускается, значит у нас уже есть одна галочка в subject.

`minikube addons list` — показывает список дополнительных опций. Тут вы найдете MetalLb, который необходимо использовать по сабжекту.

`minikube addons enable metallb` — включит metallb в нашем Kubernetes.


    kubectl apply -f [name].yaml
    kubectl delete pods [name]
    kubectl get pod
    kubectl get svc
    kubectl get pvc
    kubectl get pv
    kubectl cp grafana-deployment-[name]:/usr/share/grafana/data/grafana.db[path from db] ~/42curs/ft_services/srcs/Grafana/grafana.db[path to db] - сохранить базу данных
    kubectl describe pods [name] - расширенные логи
    kubectl logs [name] - логи