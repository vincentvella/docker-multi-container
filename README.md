Dockerizing MongoDB Database:
```docker run --name mongodb --rm -d -p 27017:27017  mongo```

Build Docker Backend:
```docker build -t goals-node .```
Run Docker Frontend:
```docker run --name goals-backend -d --rm -p 80:80 goals-node```

Build Docker Frontend: