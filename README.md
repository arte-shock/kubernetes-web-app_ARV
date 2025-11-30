# kubernetes-web-app_ARV
Kubernetes project with web app and MongoDB
Простой веб проект на Kubernetes, демонстрирующий развёртывание веб приложения с базой данных MongoDB. 
Проект использует стандартные механизмы Kubernetes: Deployments, Services, Volumes.

Проект включает:

- **Веб приложение** (на базе `nginx:alpine`) — отображает статическую страницу;
- **MongoDB** — база данных для хранения данных (в режиме single instance);
- **Volumes** — временное хранилище `emptyDir` для данных приложения и БД;
- **Service типа NodePort** — публикация веб приложения на порту `30080`.

Назначение: 
Учебный пример для освоения базовых концепций Kubernetes.

Структура проекта:


```
kubernetes-web-app/
├── deploy/
│   ├── deployment-app.yaml
│   ├── service-app.yaml
│   ├── deployment-mongodb.yaml
│   └── service-mongodb.yaml
└── README.md
```

Описание:
deploy/deployment-app.yaml (манифест Deployment для веб‑приложения);
deploy/service-app.yaml (манифест Service типа NodePort);
deploy/deployment-mongodb.yaml (манифест Deployment для MongoDB);
deploy/service-mongodb.yaml (манифест Service для MongoDB);
README.md (описание проекта, инструкции по запуску).


Как запустить

Примените манифест:
  
   kubectl apply -f deploy/
