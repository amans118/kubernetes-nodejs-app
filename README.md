# kubernetes-nodejs-app
Project which deploys a nodejs application using a image from a private AWS ECR registry and exposes it using a Classic LoadBalancer.

* If testing the manifest on a cluster setup using local vm's on Virtualbox, make sure to pass these arguments inside metrics-server.yaml
```bash
containers:
- name: metrics-server
  image: k8s.gcr.io/metrics-server-amd64:v0.3.6
  imagePullPolicy: IfNotPresent
  args:
    - --cert-dir=/tmp
    - --secure-port=4443
    - --kubelet-insecure-tls
    - --kubelet-preferred-address-types=InternalIP,Hostname,InternalDNS,ExternalDNS,ExternalIP
```
