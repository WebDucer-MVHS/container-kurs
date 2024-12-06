# Commands sheet

- ngix plain container
  ```bash
  docker run --name mein-server -p 1080:80 -d nginx:alpine
  ```
- stop nginx container
  ```bash
  docker stop mein-server
  ````
- delete nginx container
  ```bash
  docker rm mein-server
  ````
- start nginx with own website
  ```bash
  docker run --name mein-server -p 1080:80 -v /Users/schulung/src/container-kurs/nginx-site:/usr/share/nginx/html:ro -d nginx:alpine
  ```
- start .Net application
  ```bash
  dotnet run
  ````
- start Postgres container
  ```bash
  docker run -e POSTGRES_USER=devuser -e POSTGRES_PASSWORD=devpassword -e POSTGRES_DB=devdb -p 5432:5432 -d postgres:17-alpine
  ````
- start .Net application
  ```bash
  dotnet run
  ````
- start with docker compose
  ```bash
  docker compose up -d
  ```