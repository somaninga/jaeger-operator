# install default static - cert-manager
https://cert-manager.io/docs/installation/#default-static-install

kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.7.1/cert-manager.yaml


# Installing the Operator on Kubernetes

kubectl create namespace observability

kubectl create -f https://github.com/jaegertracing/jaeger-operator/releases/download/v1.31.0/jaeger-operator.yaml -n observability      

# 

kubectl apply -f - << EOL
apiVersion: jaegertracing.io/v1
kind: Jaeger
metadata:
  name: metrics-jaeger
EOL


kubectl port-forward service/metrics-jaeger-query --address 0.0.0.0 16686:16686

#### This article for having an overall idea ####
https://medium.com/velotio-perspectives/a-comprehensive-tutorial-to-implementing-opentracing-with-jaeger-a01752e1a8ce

#### this is how to use opentracing ( standard that is used by jaeger to get traces ) in javascript ####

https://github.com/opentracing/opentracing-javascript

#### These are all libraries client to jaeger ####

https://www.jaegertracing.io/docs/1.33/client-libraries/


##### this is how you inject sidecar

https://www.jaegertracing.io/docs/1.33/operator/
and
refer image

##### This is the official open telemetry library for nodejs
https://opentelemetry.io/docs/instrumentation/js/getting-started/nodejs/

###### this is a tutorial
https://selvaganesh93.medium.com/tracing-node-js-application-with-opentelemetry-jaeger-ui-9523c0ac8453


### Commands ###
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.7.1/cert-manager.yaml

k get all -n cert-manager

kubectl create namespace observability
kubectl create -f https://github.com/jaegertracing/jaeger-operator/releases/download/v1.31.0/jaeger-operator.yaml -n observability

k get all -n observability

kubectl get deployment jaeger-operator -n observability

kubectl get pod
kubectl apply -f - << EOL
apiVersion: jaegertracing.io/v1
kind: Jaeger
metadata:
    name: metrics-jaeger
EOL

k get all
kubectl port-forward service/metrics-jaeger-query --address 0.0.0.0 16686:16686