# kubernetes-web-app_ARV
Kubernetes project with web app and MongoDB
Простой веб проект на Kubernetes, демонстрирующий развёртывание веб приложения с базой данных MongoDB. 
Проект использует стандартные механизмы Kubernetes: Deployments, Services, Volumes.

Проект включает:

- **Веб приложение** (на базе `nginx:alpine`) — отображает статическую страницу, с кнопкой, при нажатии запускается ролик;
- **MongoDB** — база данных для хранения данных (в режиме single instance);
- **Volumes** — временное хранилище `emptyDir` для данных приложения и БД;
- **Service типа NodePort** — публикация веб приложения на порту `30080`.

Назначение: 
Учебный пример для освоения базовых концепций Kubernetes.

Структура проекта:

```
kubernetes-web-app/
├── deploy/
│   ├── configmap-nginx.yaml
│   ├── deployment-app.yaml
│   ├── service-app.yaml
│   ├── deployment-mongodb.yaml
│   └── service-mongodb.yaml
├── files/
│   ├── back.jpg
│   ├── button.jpg
│   └── review.mp4
├── html/
│   └── index.html
└── README.md
```

Описание:
```
deploy/deployment-app.yaml (манифест Deployment для веб‑приложения);
deploy/service-app.yaml (манифест Service типа NodePort);
deploy/deployment-mongodb.yaml (манифест Deployment для MongoDB);
deploy/service-mongodb.yaml (манифест Service для MongoDB);
files/ (контент для страницы);
html/  (статическая страница);
README.md (описание проекта, инструкции по запуску). 
```
Для запуска примените манифест:
```
   git clone https://github.com/arte-shock/kubernetes-web-app_ARV.git
   kubectl apply -f deploy/
   kubecget pod
   kubectl port-forward web-app-*** 8080:80
   http://localhost:8080 → открывает страницу с контентом.
```
