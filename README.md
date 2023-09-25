# kubernetes-studies

### Install kubectl

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

```
chmod +x kubectl
```

```
mv kubectl /usr/local/bin
```

### Install kind

```
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64
```

```
chmod +x kind
```

```
mv kind /usr/local/bin
```

```
kind create cluster --name rbx
```

```
kind delete cluster --name rbx
```

### Config completion

```
kubectl completion bash > ~/.kube/completion.bash.inc
```

# ~/.profile

> source /root/.kube/completion.bash.inc

> alias k="kubectl"

```
source ~/.profile
```

# First cluster

```
kind create cluster --config meu-primeiro-cluster.yaml --name rbx
```

# First pod

```
kubectl run --image nginx --port 80 rbx --dry-run=client -o yaml
```

```
mv pod.yaml meu-primeiro-pod.yaml
```

```
kubectl apply -f meu-primeiro-pod.yaml
```