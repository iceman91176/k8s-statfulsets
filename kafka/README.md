# Kubernetes Kafka
This is a Dockerimage + Manifest for running Apache Kafka on OpenShift/K8S. It is based on wurstmeister/kafka.
Kafka-Brokers can be accessed internally as well as externally. For external access Per-Pod-LoadBalanced-Services PLUS external-dns is used
 
## Build Docker-Image
Build and push with ```make```

## Build with Openshift
Use openshift_build.yaml to build the Image in Openshift and push to internal registry

## Deploy to Openshift
Prerequisites: Working implementation of external-dns & LoadBalanced-Services for outside-access
Apply kafka.yaml
The provided manifest scales 2 brokers. I u need more, add a LoadBalanced-Service for each broker 

