# k8s-local-setup
# Install vagrant : https://developer.hashicorp.com/vagrant/downloads

# Production setup on local using kubeadm
https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/

# Clone this repo and do gitbash
vagrant up
vagrant ssh kubemaster

# To test the cluster
kubectl create deployment hello-kubeadm --image=registry.k8s.io/e2e-test-images/agnhost:2.39 -- /agnhost netexec --http-port=8080
kubectl get deployments
kubectl get pods
kubectl expose deployment hello-kubeadm --type=LoadBalancer --port=8080
kubectl get services
kubectl describe pod <pod-name>
# Search with node ip:nodeport to check the connection
