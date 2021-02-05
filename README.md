Create network:
```docker create network goals-net```

Dockerizing MongoDB Database:
```docker run --name mongodb --rm -d --network goals-net  mongo```

Build Docker Backend:
```docker build -t goals-node .```
Run Docker Backend:
```docker run --name goals-backend -d --rm --network goals-net -p 80:80 goals-node```

Build Docker Frontend:
```docker build -t goals-react .```
Run Docker Frontend:
```docker run -it --name goals-frontend --rm -p 3000:3000 goals-react```