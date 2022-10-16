# Ingress comparison


## About

This is to highlight that HAProxy incorrectly logs the Kubernetes
Node IP as the Client IP when deployed as an Edge
A kubernetes cluster configuration that will run...


HA Proxy (As Edge Ingress/Kubernetes Service) : 2080/2443
NGinx (As Edge Ingress/LB) : 1080/1443
Istio (As Edge Ingress/LB) : 80/443

... these point to ...

Istio (As VirtualService/Gateway)

... which points to ...

Helloworld in a Pod


## Usage

```
 vagrant up
```

The output you'll see will set up the multiple ingress controller types, and make a request to each. It will then
also scrape the logs of each ingress controller pod to highlight that both Istio and Nginx handle the logging of a
Client IP correctly.


## Deploy to Cloud

ansible-playbook playbook-cloud.yml -i inventory
