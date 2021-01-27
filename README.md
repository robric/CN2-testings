# Cloud Native Contrail Early Testings on my Windows Laptop

##  Contrail turns into a Kubernetees-native application !

These days, we're taking Contrail and making it truly kubernetees-native.
This is a major change in our configuration plane, as contrail logic is being migrated to the kube API thanks to custom ressources.
This will make Contrail being as easy to consume as any application. Install it, take your manifest to buid your networking logic and here you go: you get advanced container routing with advanced networking functionalities.

For example, the definition of a BGP peer toward  - For networkers, check out the rich afi/safi support (address-family) and figure out how  connectivity becomes simple thanks to a nativeintegration in the MP-BGP contol plane.

```
cat mx.yaml
apiVersion: core.contrail.juniper.net/v1alpha1
kind: BGPRouter
metadata:
  name: mx
  namespace: default-project
spec:
  bgpRouterParameters:
    address: 192.168.39.254
    addressFamilies:
      family:
      - inet
      - inet-labeled
      - inet-vpn
      - e-vpn
      - erm-vpn
      - route-target
      - inet6
      - inet-mvpn
      - inet6-vpn
    autonomousSystem: 64512
    identifier: 192.168.39.254
    port: 179
    routerType: router
    vendor: Juniper
  bgpRouterReferences:
  - apiVersion: core.contrail.juniper.net/v1alpha1
    attributes: {}
    fqName:
    - default-domain
    - default-project
    - ip-fabric
    - default
    - minikube
    kind: BGPRouter
    name: minikube
    namespace: default-project
  parent:
    apiVersion: core.contrail.juniper.net/v1alpha1
    kind: RoutingInstance
    name: default
    namespace: default-project
```

And there is much more to come, but ush ush :-)

Hence I am pretty exciting to test the kubernetees-native routing platform. Right now builds are Juniper-internal, but stay tuned :-).

## Installation procedure

Let's first start to install microk8s.

I just downloaded the microk8S installer from https://microk8s.io/

