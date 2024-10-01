# quickstart

### Apply schema
```
oc apply -k .
```

### Create a new XR (Composite resource) instance
```
oc apply -f xr-foo.yaml
```

### Show Results:
```
 oc get managed
NAME                                             KIND        PROVIDERCONFIG        SYNCED   READY   AGE
object.kubernetes.crossplane.io/toms-foo-v4j4p   Namespace   kubernetes-provider   True     True    3d16h


# get the resulting K8s object created: my foo namespace!

╰─ oc get ns| grep foo
crossplane-managed-foo                             Active   3d16h


## using beta feature of CLI:

╰─ crossplane beta trace CompositeFoobar toms-foo -o wide
NAME                       RESOURCE   SYNCED   READY   STATUS
CompositeFoobar/toms-foo              True     True    Available
└─ Object/toms-foo-v4j4p              True     True    Available
```

