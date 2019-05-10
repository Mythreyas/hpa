# Horizontal Pod autoscaler

##  Pre-requisite

##  Install Metrics server - 

> Clone this repository and install metrics server. Please do note that this setup is good for dev/qa environment. A lot of considerations must be put while installing metrics server in production environment. The official metrics-server repository is kept at https://github.com/kubernetes-incubator/metrics-server and we are using the same repo with few changes. 

> The file `metrics-server-deployment.yaml` is edited with the below statements - 

~~~
        command:
        - /metrics-server
        - --kubelet-insecure-tls
        - --kubelet-preferred-address-types=InternalIP

~~~

> The above command has the flag `--kubelet-insecure-tls` set which ignores strict check of kubelet certificates. In production you will definitely have a single CA private key that will be used to sign all kubelets. Please check the official metrics server documentation on other flags. 

> Install the metrics server 

` cd metrics-server` 

` kubectl create -f . ` 
