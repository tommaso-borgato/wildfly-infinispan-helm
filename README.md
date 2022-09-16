helm repo add wildfly https://docs.wildfly.org/wildfly-charts/
helm repo add openshift-helm-charts https://charts.openshift.io/
helm dependency build

oc new-project helm-test
helm install wildfly-infinispan .

helm uninstall wildfly-infinispan
oc delete project helm-test