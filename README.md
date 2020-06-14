# kubernetes-certificate-secret-manage
kubernetes-certificate-secret-manage

~~~
kubectl apply -f nginx1-dep.yaml
kubectl apply -f nginx2-dep.yaml

and service .......
~~~

openssl genrsa  -out nginx1.key 2048
openssl req -new -key nginx1.key -out nginx1.csr
openssl x509 -req -days 365 -in nginx1.csr -signkey nginx1.key -out nginx1.crt

 kubectl create secret tls nginx-1-secret --cert nginx1.crt --key nginx1.key
 
 kubectl get secret
 kubectl describe  secret nginx-1-secret
