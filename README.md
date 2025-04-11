# k8s-local-setup

# Minikube setup : single node cluster for local test environment
# https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

# Run on windows powershell 
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) on windows powershell.

# Close current session of powershell, restart it with admin access 
$ choco install minikube kubernetes-cli -y

# Open Git bash and enter below commands.
$ cd ~
$ minikube.exe --help
$ minikube start

# If getting this error : Exiting due to HOST_VIRT_UNAVAILABLE: Failed to start host: creating host: create: precreate: This computer doesn't have VT-X/AMD-v enabled. Enabling it in the BIOS is mandatory follow below steps :

# Start docker desktop and run below commands on gitbash.
$ cd ~
$ minikube delete
$ minikube start --driver=docker
$ kubectl get nodes
$ cat ./kube/config
