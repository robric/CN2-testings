# Cloud Native Contrail Early Testings on my Windows Laptop

##  Contrail turns into Kubernetees native application

These days, we're taking Contrail and making it truly kubernetees-native.
This is a major change in our configuration plane, as contrail logic is being migrated to the kube API thanks to custom ressources.
This will make Contrail being as easy to consume as any application. Install it, take your manifest to buid your networking logic and here you go: you get advanced container routing with advanced networking functionalities.

Hence I am pretty exciting to test the kubernetees-native routing platform. Right now builds are Juniper-internal, but stay tuned :-).

## Installation procedure

Let's first start to install microk8s.

We're taking Contrail and making it truly kubernetees-native.

I just downloaded the microk8S installer from https://microk8s.io/

