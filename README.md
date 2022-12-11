# cert-manager-dns01-exmple

helm等でcert-managerとnginx-ingress-controllerをインストールする。

route53のSecret access keyを登録する。
```
kubectl -n  cert-manager create secret generic prod-route53-credentials-secret --from-literal=secret-access-key=<SECRET_ACCESS_KEY>
```

letsencrypte-issuerのemailとaccessKeyIDを書き換える。
```
kubectl apply -f deployment.yaml

kubectl apply -f service.yaml

kubectl apply -f letsencrypte-issuer.yaml

kubectl apply -f certificate.yaml

kubectl apply -f ingress.yaml
```

デバッグ
```
kubectl describe || certificate  || certificateRequest || order || hallenge
```