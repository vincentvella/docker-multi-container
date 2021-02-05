Create network:
```docker create network goals-net```

Dockerizing MongoDB Database:
```docker run --name mongodb --rm -d --network goals-net -v data:/data/db -e MONGO_INITDB_ROOT_USERNAME=vince -e MONGO_INITDB_ROOT_PASSWORD=secret mongo```

Build Docker Backend:
```docker build -t goals-node .```
Run Docker Backend:
```docker run --name goals-backend -d --rm --network goals-net -v /Users/vvella/Workspace/Kubernetes/docker-multi-container/backend:/usr/src/app -v logs:/usr/src/app/logs -v /usr/src/app/node_modules  -p 80:80 goals-node```

Build Docker Frontend:
```docker build -t goals-react .```
Run Docker Frontend:
```docker run -it --name goals-frontend --rm -p 3000:3000 goals-react```