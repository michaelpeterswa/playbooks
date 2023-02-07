## Post Install Commands

https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-certs/#kubelet-serving-certs

* `kubectl label node vm-wk-1 node-role.kubernetes.io/worker=worker`
* `kubectl label node vm-wk-2 node-role.kubernetes.io/worker=worker`
* `kubectl label node vm-wk-3 node-role.kubernetes.io/worker=worker`
* `kubectl label node vm-wk-4 node-role.kubernetes.io/worker=worker`
* `istioctl install`
* `kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml`
* `kubectl get configmap kube-proxy -n kube-system -o yaml | \
sed -e "s/strictARP: false/strictARP: true/" | \
kubectl apply -f - -n kube-system`
* `kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.7/config/manifests/metallb-native.yaml`