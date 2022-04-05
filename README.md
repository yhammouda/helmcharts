# helmcharts
kubectl delete -f others/
kubectl apply -f others/

helm install redis charts/redis/
helm install api charts/api/

curl http://api.kub/api/v1/list
curl --header "Content-Type: application/json" --request POST --data '{"name":"pipo", "city":"Paris", "age":"32"}' api.kub/api/v1/insert

helm package charts/{api,redis} --destination releases
(cd .. && helm repo index helmcharts)