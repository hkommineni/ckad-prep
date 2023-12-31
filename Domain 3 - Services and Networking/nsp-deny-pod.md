#### Create a Test App Pod01 from a terminal
```sh
kubectl run -it pod01 --image=busybox 
```

#### Create a Pod02 from a different terminal
```sh
kubectl run -it pod02 --image=busybox 
```

#### Get IP Address of pod01
```sh
ifconfig
```

#### ping pod01 from pod02
```sh
ping <pod01_ip_address> 
```

#### Create a NetowrkPolicy Template
```sh
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-pod
  namespace: default
spec:
  podSelector:
    matchLabels:
        run: pod01
  policyTypes:
  - Ingress
  - Egress
```
