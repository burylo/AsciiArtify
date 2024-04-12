# ArgoCD POC


#### Вступ

Для запуску ArgoCD локально потрібно виконати наступні кроки:

 - Створити новий *namespace* для локалізації застосунку:
    ````kubectl create namespace argocd````
- Встановити ArgoCD:
   ```kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml```
- Змінити argocd-server сервіс тип на *LoadBalancer*
  ``kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'``
 - Зробити перенаправлення порту
   ``kubectl port-forward svc/argocd-server -n argocd 8080:443``

Після цього сервіс ArgoCD буде доступний в браузері на порту *8080*

    https://localhost:8080

#### Демо доступу до ArgoCD Web UI
[![ArgoCD_POC](./gif/ArgoPOC.gif)]()