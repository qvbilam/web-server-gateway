### 确认拓展
```shell
$ kubectl get svc -n istio-system | grep istio-ingressgateway
istio-ingressgateway   LoadBalancer   10.96.188.52    <pending>     15021:31481/TCP,80:32078/TCP,443:31694/TCP,31400:32557/TCP,15443:30750/TCP   8d
```

### 申请网格配置
```shell
$ kubectl apply -f serviceEntry.yml

$ kubectl apply -f gateway.yml

$ kubectl apply -f virtualService.yml
```

### 本地调试启动
```shell
# 通过访问 localhost:8080 访问
$ kubectl port-forward -n istio-system svc/istio-ingressgateway 8080:80
```