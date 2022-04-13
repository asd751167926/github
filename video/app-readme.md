# videoService

video服务

## How to Use It
### [Ingress-shim](https://cert-manager.readthedocs.io/en/latest/reference/ingress-shim.html#ingress-shim)
Cert-manager will create Certificate resources that reference the `ClusterIssuer` for all Ingresses that have following annotations.
```
kubernetes.io/tls-acme: "true"
certmanager.k8s.io/cluster-issuer: letsencrypt-staging # your cluerissuer name
nginx.ingress.kubernetes.io/secure-backends: "true" # optional
```

For cert-manager to work properly, the following information has to be added on your ingress definition.
```
spec:
  tls:
  - hosts:
    - host.example.com
    secretName: host-example-crt
```