oc new-project myosproject
oc project myosproject

oc create -f buildconfig.yaml
oc create imagestream nginx-hello-world
oc start-build nginx-hello-world --from-dir=./ --follow
oc get imagestream nginx-hello-world

oc create -f deployment.yaml
oc get deployment nginx-hello-world
oc get pods

oc apply -f service.yaml

oc expose svc/nginx-hello-world