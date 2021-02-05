Dockerizing MongoDB Database:
```docker run --name mongodb --rm -d -p 27017:27017  mongo```

Build Docker Backend:
```docker build -t goals-node .```
Run Docker Backend:
```docker run --name goals-backend -d --rm -p 80:80 goals-node```

Build Docker Frontend:
```docker build -t goals-react .```
Run Docker Frontend:
```docker run -it --name goals-frontend --rm -p 3000:3000 goals-react```