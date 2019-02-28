# Kubernetes
---

**AutoComplete** `source <(kubectl completion bash)`

## Let's install Kubectl

### Linux:

 `curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

**Now give the permitions and move to /usr/local/bin**

`chmod +x kubectl && mv kubectl /usr/local/bin/`

### MacOs:

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/darwin/amd64/kubectl

**Now give the permitions and move to /usr/local/bin**

`chmod +x kubectl && mv kubectl /usr/local/bin/`

If you prefer you can install by `brew install kubectl`

### WINDOWS:

`curl -Lo https://storage.googleapis.com/kubernetes-release/release/v1.9.0/bin/windows/amd64/kubectl.exe`


[https://kubernetes.io/docs/tasks/tools/install-minikube/](URL)

## Let's install MINIKUBE

### LINUX:

`curl -Lo minikube https://github.com/kubernetes/minikube/releases/download/v0.28.0/minikube-linux-amd64`

**Now give the permitions and move to /usr/local/bin**

`chmod +x minikube && mv minikube /usr/local/bin/`

### MacOs:

`curl -Lo minikube https://github.com/kubernetes/minikube/releases/download/v0.28.0/minikube-darwin-amd64`

**Now give the permitions and move to /usr/local/bin**

 `chmod +x minikube && mv minikube /usr/local/bin/`


### WINDOWS:

[https://github.com/kubernetes/minikube/releases/download/v0.25.0/minikube-windows-amd64](URL)
##Let's start the MINIKUBE:

`minikube start`

### To view all NODE

`kubectl get nodes`

**Let's run our firt command with kubectl:**

`kubectl run nginx --image nginx`

`kubectl get deployment`

`kubectl get pods`



**We're going to use google cloud.**

[https://cloud.google.com/](URL)

**Let's create our clusters with google cloud:**

##After create 3 clusters and connect to ssh

**Let's install Docker**

`curl -fsSL https://get.docker.com | bash`

**Install Kubernetes**

`apt update && apt install -y apt-transport-https`

**let's add the key to our  google**

`curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -`



**Create list kubernetes connected to source.list**

` echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" > /etc/apt/sources.list.d/kubernetes.list`


One Update:

`apt update`

**And Now we have to install kubelet kubeadm and kubectl**

`apt install -y kubelet kubeadm kubectl`

####Before start our cluster don't forget to  turnof the swap

`swapoff -a`

If you want to  turn of forever  go to `nano /etc/fstab` and
put in comment.

## let's start our server.

**In the first machine run:**

`kubeadm init --apiserver-advertise-address $(hostname -i)`

**Create a folder**

`mkdir -p $HOME/.kube`

**we have to copie the files to this folder**

` sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`

**And now we have to give the permitions**

`sudo chown $(id -u):$(id -g) $HOME/.kube/config`

**Copie the address in our terminal is the last kubeadm join ....**

**And Now Paste in the others machine:**

**In the master machine run this command to see all machines connect (nodes)**



`kubectl get nodes`

## If the status is NotReady run:

**to have all the pods network**

`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`


**Now run again in the master machine**

`kubectl get nodes`

**To Know more about the node**

`kubectl describe nodes {name}`

**To see the pods of kubernetes**

`kubectl get pods -n kube-sytem`

**To Know more about the pod**

`kubectl describe pod {name pod kube-apiserver} -n kube-system`

**To find the ip:**

`kubectl get pods -o wide -n kube-system`

**To see all the deployments:**

`kubectl get deployments`

**To remove one deployments**

`kubectl delete deployments {deploymentName}`

**If you want to take all pods inside all namespaces:**

`kubectl get pods --all-namespaces`

**Let's create 10 replicas of nginx**

`kubectl run nginx --image nginx --replicas 10`

**Let's see where are the replicas**

`kubectl get pods -o wide








