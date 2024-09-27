curl -sLO https://cli.upbound.io/stable/current/bin/linux_amd64/up

```
oc new-project crossplane-system
helm repo add crossplane https://charts.crossplane.io/stable
helm repo update
```


```
helm install crossplane -n crossplane-system crossplane/crossplane \
 --set securityContextCrossplane.runAsUser=null \
 --set securityContextCrossplane.runAsGroup=null \
 --set securityContextRBACManager.runAsUser=null \
 --set securityContextRBACManager.runAsGroup=null
```


Maybe also install providers via chart?:
```
--set provider.packages='{xpkg.upbound.io/crossplane-contrib/provider-aws:v0.39.0}'
```
