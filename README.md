**kubeplugin** is a bash script that extends the functionality of the `kubectl top` command. It allows you to retrieve CPU and memory usage statistics for `pods` and `nodes` of a specified namespace in your K8s cluster.

# Installing kubeplugin

1. **Clone the repository to your local machine.**
```
git clone https://github.com/andrefanatic/kubeplugin.git
```
2. **Navigate to the directory containing the script.**
```
cd kubeplugin/scripts
```
3. **Make the script executable.**
```
chmod +x kubeplugin
```
4. **Move the script to the directory where other kubectl plugins are located.** (For example, on Unix-like systems, it might be /usr/local/bin/)
```
sudo mv kubeplugin /usr/local/bin/
```
5. **Execute the script with the desired arguments.**
```
kubeplugin <node or pod> <namespace>
```
Replace <node or pod> with the type of resource you want to query (e.g., node or pod), and <namespace> with the namespace you want to query. 

**Example of usage**
```
➜  ~ k kubeplugin pod kube-system
RESOURCE_TYPE   NAMESPACE       NAME                                          CPU        MEMORY
pod             kube-system     coredns-6799fbcd5-5nhbw                       4m         23Mi
pod             kube-system     local-path-provisioner-6c86858495-6lmb6       1m         12Mi
pod             kube-system     metrics-server-54fd9b65b-sgxsf                7m         26Mi
pod             kube-system     svclb-traefik-4439f96f-7s4vt                  0m         0Mi
pod             kube-system     traefik-f4564c4f4-ppmsm                       1m         37Mi
```

```
➜  ~ k kubeplugin node kube-system
RESOURCE_TYPE   NAMESPACE       NAME                                          CPU        MEMORY
node            kube-system     k3d-demo-server-0                             149m       1%
```

