#### Step 1: Create a new pod:

```sh
kubectl run -it ubuntu --image=ubuntu
service nginx status
kubectl get pods
kubectl exec -it ubuntu service nginx status
```
livenessprobe.yaml

```sh
apiVersion: v1
kind: Pod
metadata:
  name: liveness
spec:
  containers:
  - name: liveness
    image: ubuntu
    tty: true
    livenessProbe:
      exec:
        command:
        - service
        - nginx
        - status
      initialDelaySeconds: 20
      periodSeconds: 5
```

```sh
kubectl apply -f livenessprobe.yaml
kubectl exec -it liveness service nginx status
```
