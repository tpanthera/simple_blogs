
# Istio :

open source service mesh that layers transparently onto existing distributed applications.
The term service mesh is used to describe the network of microservices that make up such applications and the interactions between them

Istio is a component built on top of Envoy (proxy like ngnix that also enable supports http2.0 & GRPC for k8 ).

Istio makes it easy to create a network of deployed services with load balancing, service-to-service authentication, monitoring, and more, with few or no code changes in service code. 

Architecture

An Istio service mesh is logically split into a data plane and a control plane.

The data plane is composed of a set of intelligent proxies (Envoy) deployed as sidecars. These proxies mediate and control all network communication between microservices along with Mixer, a general-purpose policy and telemetry hub.

The control plane manages and configures the proxies to route traffic. Additionally, the control plane configures Mixers to enforce policies and collect telemetry.

Implementation ::::

# once instio installed some features ---

# Whitelisting URL 
by default everything is blocked going out of the cluster . 
!!! to whitelist some url , we need to implement below 
need to put 'egress rule' in yaml .
Kind : egress rule 
spec : 
   destination :
      service : time.jsontest.com 
-- this will allow traffic to time.jsontest.com


# Kubernetes follow round robin load balancing for its services ,
  issue is it will send traffic to tags (same tags can be present for different environment), 
  istio can make traffic go where we want !!
  for that there is something call route rule ..

# Istio 'simpleretry' policy , masking the failures , 
for some reason if services are failing , isitio will check with no. of retries set in simpleretry .
That retry will be unknown to i/p request

# Selective routing , istio dashboard (is important feature )   

there are also something called kuberentes federation API , zipkin (distributed tracing )


https://www.youtube.com/watch?v=gauOI0O9fRM
https://glasnostic.com/blog/kubernetes-service-mesh-what-is-istio
https://thenewstack.io/microservicing-with-envoy-istio-and-kubernetes/   (good explanation from red hat)
https://istio.io/docs/concepts/what-is-istio/


https://kublr.com/blog/implementing-a-service-mesh-with-istio-to-simplify-microservices-communication/ (detail)
https://www.bizety.com/2018/10/17/spinnaker-vs-jenkins/
https://blog.getambassador.io/envoy-vs-nginx-vs-haproxy-why-the-open-source-ambassador-api-gateway-chose-envoy-23826aed79ef
envoy-istio-and-kubernetes/
https://www.youtube.com/watch?v=kKC-VgAptII

---
 taping the information 
 front-end fail / pass ?
 middleware fail / pass ?
 backend failed / pass ??

