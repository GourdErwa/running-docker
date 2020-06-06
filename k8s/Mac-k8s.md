
## Dashboard 网页界面
文档 [网页界面 (Dashboard)](https://kubernetes.io/zh/docs/tasks/access-application-cluster/web-ui-dashboard/) ，

部署命令: `kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml` 
访问不成功时需要手动粘贴内容 [v2.0.0-recommended](./v2.0.0-recommended.yaml) 进行执行。

命令行代理：`kubectl proxy`

访问：`http://127.0.0.1:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login`

### Kubernetes-token
```shell script
# 查看所有账号
kubectl -n kube-system get sa

# 以 default 账号为例 取 secrets

kubectl -n kube-system get sa default -o yaml

# 查 token
kubectl get secrets default-token-r95vm -n kube-system -oyaml


# 取具体的 token 值
kubectl get secrets default-token-r95vm -n kube-system -o jsonpath={".data.token"}

# token 转码
kubectl get secrets default-token-r95vm -n kube-system -o jsonpath={".data.token"} | base64 -d

# eyJhbGciOiJSUzI1NiIsImtpZCI6ImhkNkhxRUM1b1lHLTZ5WU5jS1M5R29mZU9wQWg4TENmQzFkRk5UUWszQTAifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJkZWZhdWx0LXRva2VuLXI5NXZtIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlZmF1bHQiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiI1ZWQxZjU5My0xODRjLTRhMmItYmVjYi1iNzIxZGNjOWUyODgiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6a3ViZS1zeXN0ZW06ZGVmYXVsdCJ9.oPL3RWIUni3508RgSWHh3ORvUOL5hBZKkaQEkK_aKRHVzJIgLyWo72zpSEIoZgVGzrkHSPjE4vvkdygZm2flibOm2l7F7YCtZ0sCh4WbdnSMgXQuUx9uB72kLyl9zjgFaDvRFFdFklhfSukpRwVUlrF78hW9gJ5Jr6gNGbDIXpX-nj7tbA6f6uTqi5dQCysZPneIFD1UjmUIad_oTvaQ3F1qnQ3-V9F6_d4N-XGao5c-Mao1EWGRfVtlLxA9-w5y4Sw5pCSi2fMtxOvC3_x3z0TwRgrOKaTRCNPJh1yr_ejIMKoqzp7jMVqiVFScG6c4QsN8MIVpKMMPjeAZOgaTpg
```