# Readme

docker-compose -f stack.yml

kubectl apply -f k8s.yml

kubectl port-forward service/bonita-app 7080:8080

---
### Get Pod name

POD=$(kubectl get pod -o jsonpath="{.items[0].metadata.name}")

kubectl -it exec $POD -- bash

### Get log 
kubectl logs $POD
kubectl get cm
kubectl exec $POD -- ls /etc/logging.properties
kubectl exec $POD -- cat /etc/logging.properties


kubectl exec $POD -- tail -f /opt/bonita/BonitaCommunity-2021.1/server/logs/bonita.`date +%Y-%m-%d`.log

kubectl exec $POD -- ls /opt/custom-init.d
kubectl exec $POD -- cat /opt/bonita/BonitaCommunity-2021.1/server/conf/logging.properties