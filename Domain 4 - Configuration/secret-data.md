##### secret-data.yaml

```sh
apiVersion: v1
kind: Secret
metadata:
  name: thirdsecret
type: Opaque
data:
  username: ZGJhZG1pbg==
  password: bXlwYXNzd29yZDEyMw==
```

##### secret-stringdata.yaml

```sh
apiVersion: v1
kind: Secret
metadata:
  name: stringdata
type: Opaque
stringData:
  config.yaml: |-
    username: ZGJhZG1pbg==
    password: dGhpc2lzdGhpcmRzZWNyZXQ=

```
